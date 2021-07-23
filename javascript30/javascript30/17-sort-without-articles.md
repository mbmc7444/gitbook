# 17 - Sort Without Articles

{% tabs %}
{% tab title="HTML" %}
```markup
  <title>Sort Without Articles</title>
```
{% endtab %}

{% tab title="CSS" %}
```css
 body {
      margin: 0;
      font-family: sans-serif;
      background: url("https://source.unsplash.com/nDqA4d5NL0k/2000x2000");
      background-size: cover;
      display: flex;
      align-items: center;
      min-height: 100vh;
    }

    #bands {
      list-style: inside square;
      font-size: 20px;
      background: white;
      width: 500px;
      margin: auto;
      padding: 0;
      box-shadow: 0 0 0 20px rgba(0, 0, 0, 0.05);
    }
    
    #bands li {
      border-bottom: 1px solid #efefef;
      padding: 20px;
    }
    
    #bands li:last-child {
      border-bottom: 0;
    }

    a {
      color: #ffc600;
      text-decoration: none;
    }

```
{% endtab %}

{% tab title="JS" %}
```javascript
const bands = ['The Plot in You', 'The Devil Wears Prada', 'Pierce the Veil', 'Norma Jean', 'The Bled', 'Say Anything', 'The Midway State', 'We Came as Romans', 'Counterparts', 'Oh, Sleeper', 'A Skylit Drive', 'Anywhere But Here', 'An Old Dog'];

function strip(bandName) {
  return bandName.replace(/^(a |the |an )/i, '').trim();
}

const sortedBands = bands.sort((a, b) => strip(a) > strip(b) ? 1 : -1);

document.querySelector('#bands').innerHTML =
  sortedBands
    .map(band => `<li>${band}</li>`)
    .join('');

console.log(sortedBands);

```
{% endtab %}
{% endtabs %}

bans 배열을 각각 정렬 하려는 코드이다.  문제는 A , THE ,AN 같은 문자열을 제거하고 배열하는것이기 때문에 정규 표현식을 사용하였다.

```javascript
function strip(bandName) {
  return bandName.replace(/^(a |the |an )/i, '').trim();
}

```

 strip이라는 함수에 bandName 의 인자를 넣고 그 인자로 들어온 배열에 정규표현으로 a the an을 제거하는 구문이다.  이때 혹시모를 공백을 제거하기위해 .trim\(\)해준다 .

**sort\(a,b\)**

```javascript
const sortedBands = bands.sort((a, b) => strip(a) > strip(b) ? 1 : -1);

/* 
const sortedBands = bands.sort(function(a,b){
    if(strip(a) > strip(b)){
        return 1
    } else {
        reuturn -1
    }
}) 
*/
```

이제 알파벳순서로 정렬을 하는 구문을 작성하면된다.

배열을 innerHTML 을 할때는 .join\(\) 하도록 하자

