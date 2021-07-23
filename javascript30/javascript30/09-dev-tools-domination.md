# 09 - Dev Tools Domination

{% tabs %}
{% tab title="HTML" %}
```markup
<p onClick="makeGreen()">×BREAK×DOWN×</p>
```
{% endtab %}

{% tab title="JS" %}
```javascript
  const dogs = [{ name: 'Snickers', age: 2 }, { name: 'hugo', age: 8 }];

    function makeGreen() {
      const p = document.querySelector('p');
      p.style.color = '#BADA55';
      p.style.fontSize = '50px';
    }

    // Regular
    console.log('hello');

    // Interpolated
    console.log('Hello I am a %s string!', '💩');

    // Styled
    // console.log('%c I am some great text', 'font-size:50px; background:red; text-shadow: 10px 10px 0 blue')

    // warning!
    console.warn('OH NOOO');

    // Error :|
    console.error('Shit!');

    // Info
    console.info('Crocodiles eat 3-4 people per year');

    // Testing
    const p = document.querySelector('p');

    console.assert(p.classList.contains('ouch'), 'That is wrong!');

    // clearing
    console.clear();

    // Viewing DOM Elements
    console.log(p);
    console.dir(p);

    console.clear();

    // Grouping together
    dogs.forEach(dog => {
      console.groupCollapsed(`${dog.name}`);
      console.log(`This is ${dog.name}`);
      console.log(`${dog.name} is ${dog.age} years old`);
      console.log(`${dog.name} is ${dog.age * 7} dog years old`);
      console.groupEnd(`${dog.name}`);
    });

    // counting

    console.count('Wes');
    console.count('Wes');
    console.count('Steve');
    console.count('Steve');
    console.count('Wes');
    console.count('Steve');
    console.count('Wes');
    console.count('Steve');
    console.count('Steve');
    console.count('Steve');
    console.count('Steve');
    console.count('Steve');

    // timing
    console.time('fetching data');
    fetch('https://api.github.com/users/wesbos')
      .then(data => data.json())
      .then(data => {
        console.timeEnd('fetching data');
        console.log(data);
      });

    console.table(dogs);

```
{% endtab %}
{% endtabs %}

#### Breakpoint

만약 태그 속성을 바꾸는 코드의 작성 위치를 모르겠을때 사용가능하다.

개발자 도구-&gt; 해당태그 우클릭 -&gt; Break on -&gt; attribute modifications 

**console.clear\(\)**

이전에 출력된 console이 지워진다

```javascript
console.clear() 
```

**%s , %c**

style을 주거나 단어를 바꿀수있다.

```javascript
console.log('Hello I am a %s string!', '💩');
// %s -> '💩'
console.log('%c I am some great text' ,'font-size:50px;')
//%c : 스타일을 주고싶을때 사용한다.
```

**warn , error, info**

 콘솔창에 경고 ,에러 ,정보를 띄울수있다.

```javascript
console.warn('OH NOOO');
// 경고
console.error('Shit!');
// 에러
console.info('Crocodiles eat 3-4 people per year');
// 정보
```

**assert**

참,거짓을 판단하여 console 창에 띄어준다

```javascript
console.assert(p.classList.contains('ouch'), 'That is wrong!');
/*
p의 class중에 ouch가 있는지 없는지 (참 ,거짓) 
판단하여 거짓이면 console 을찍을수있다.
*/
```

#### dir

```javascript
console.log()
// 해당엘리먼트를 확인수있다.
console.dir()
// 해당 엘리먼트의 속성이나 더많은 정보를 확인할수있다.
```

**group**

```javascript
console.group() //groupCollapsed();
console.groupEnd();
/*
배열이나 또는 관련된것들끼 합쳐서 콘솔창에 찍을수있다.
*/
```

**count**

```javascript
console.count // 콘솔창에서 찍힌 횟수를 확인할수 있다.
```

#### time

```javascript
console.time()
 console.timeEnd()
 /*
 time이 작성된 곳부터 timeEnd이 작성된 코드까지
  실행시간을 확인 할수있다.
 */
```

#### table

```javascript
   console.table(dogs);// 테이블형식으로 정리할수있다.
```

