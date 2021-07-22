# 06 - Type Ahead

{% tabs %}
{% tab title="HTML" %}
```markup
  <form class="search-form">
    <input type="text" class="search" placeholder="City or State">
    <ul class="suggestions">
      <li>Filter for a city</li>
      <li>or a state</li>
    </ul>
  </form>
```
{% endtab %}

{% tab title="CSS" %}
```css
html {
  box-sizing: border-box;
  background: #ffc600;
  font-family: 'helvetica neue';
  font-size: 20px;
  font-weight: 200;
}

*, *:before, *:after {
  box-sizing: inherit;
}

input {
  width: 100%;
  padding: 20px;
}

.search-form {
  max-width: 400px;
  margin: 50px auto;
}

input.search {
  margin: 0;
  text-align: center;
  outline: 0;
  border: 10px solid #F7F7F7;
  width: 120%;
  left: -10%;
  position: relative;
  top: 10px;
  z-index: 2;
  border-radius: 5px;
  font-size: 40px;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.12), inset 0 0 2px rgba(0, 0, 0, 0.19);
}

.suggestions {
  margin: 0;
  padding: 0;
  position: relative;
  /*perspective: 20px;*/
}

.suggestions li {
  background: white;
  list-style: none;
  border-bottom: 1px solid #D8D8D8;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.14);
  margin: 0;
  padding: 20px;
  transition: background 0.2s;
  display: flex;
  justify-content: space-between;
  text-transform: capitalize;
}

.suggestions li:nth-child(even) {
  transform: perspective(100px) rotateX(3deg) translateY(2px) scale(1.001);
  background: linear-gradient(to bottom,  #ffffff 0%,#EFEFEF 100%);
}

.suggestions li:nth-child(odd) {
  transform: perspective(100px) rotateX(-3deg) translateY(3px);
  background: linear-gradient(to top,  #ffffff 0%,#EFEFEF 100%);
}

span.population {
  font-size: 15px;
}

.hl {
  background: #ffc600;
}

```
{% endtab %}

{% tab title="JS" %}
```javascript
const endpoint = 'https://gist.githubusercontent.com/Miserlou/c5cd8364bf9b2420bb29/raw/2bf258763cdddd704f8ffd3ea9a3e81d25e2c6f6/cities.json';

const cities = [];
fetch(endpoint)
  .then(blob => blob.json())
  .then(data => cities.push(...data));

function findMatches(wordToMatch, cities) {
  return cities.filter(place => {
    const regex = new RegExp(wordToMatch, 'gi');
    return place.city.match(regex) || place.state.match(regex)
     /*
   맞는 object 들을 찾기위한 함수이다.
  - regex 를 만족하는 도시, 주 이름을 가진 경우만 리턴하게 하는 것이다.
*/
  });
}

function numberWithCommas(x) {
  return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',');
  // 3번째 자리마다 , 를 추가하는 정규표현
}

function displayMatches() {
  const matchArray = findMatches(this.value, cities);
  const html = matchArray.map(place => {
    const regex = new RegExp(this.value, 'gi');
    const cityName = place.city.replace(regex, `<span class="hl">${this.value}</span>`);
    const stateName = place.state.replace(regex, `<span class="hl">${this.value}</span>`);
    return `
      <li>
        <span class="name">${cityName}, ${stateName}</span>
        <span class="population">${numberWithCommas(place.population)}</span>
      </li>
    `;
  }).join('');
  /*
  findMatches(input에 작성된 글자를 findMatches 함수로 대)
   html에 넣어줄 값을 만든다

- replace  를 통해 검색철자를 다르게 보여주는 부분에 주목

- 리턴값이 html 들의 리스트이고, 그걸 join 으로 하나로 묶어준다.
  */
  suggestions.innerHTML = html;
}
```
{% endtab %}
{% endtabs %}

#### fetch

서버에서 api를 호출하고 그 결과값으로 데이터를 받거나 처리할때 사용한다.

```javascript
fetch(endpoint) // 데이터가 담겨있는 endpoint에서 데이터를 받아온다
  .then(blob => blob.json()) 
  // 받아온 데이터를 blob에 담고 그데이터를 json형식으로 바꾼다
  .then(data => cities.push(...data));
  // json형식으로 되어있는 값을 cities에 넣는다
```

{% hint style="info" %}
...\(Spread 연산\) es6에서 새롭게 나온 구문으로 배열에 추가 삭제 함수 인자 활용등 다양하게 사용할수있다.

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread\_syntax](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax)
{% endhint %}

```javascript

function findMatches(wordToMatch, cities) {
  return cities.filter(place => {
    const regex = new RegExp(wordToMatch, 'gi');
    return place.city.match(regex) || place.state.match(regex)
  });
}
```

\*\*\*\*

**RegExp\(\)**

정규표현식으로 만들때 사용한다.

RegExp\(a, b\)

a 는 정규표현식 문자열 이나 다른 RegExp 객체를 받을 수 있다.

b 는 g i m s y u 문자를 받을 수 있다.

* g: 문자열 전체를 확인한다.
* i: 문자열 에서 대소문자를 구분하지 않는다.
* m: 문자열 에서 `^` , `$` 에서 개행문자를 허용한다.
* s: 문자열 에서 `.` 에서 개행문자를 허용한다.
* y: lastIndex 부터 일치하는 문자열을 반환한다.
* u: Unicode 코드 포인트의 시퀀스로 처리한다.

#### 

#### replace\(\)

어떤 패턴에 일치하는 일부 또는 모든 부분이 교체된 새로운 문자열을 반환

```javascript
const p = 'The quick brown fox jumps over the lazy dog. If the dog reacted, was it really lazy?';

console.log(p.replace('dog', 'monkey'));
/*
dog -> monkey
"The quick brown fox jumps over the lazy monkey. If the dog reacted, was it really lazy?"
*/


const regex = /Dog/i;
console.log(p.replace(regex, 'ferret'));
/*
정규표현식으로 dog -> ferret
 "The quick brown fox jumps over the lazy ferret. If the dog reacted, was it really lazy?"
*/
```

#### 

