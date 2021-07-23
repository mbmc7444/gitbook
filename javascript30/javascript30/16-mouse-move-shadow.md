# 16 - Mouse Move Shadow

{% tabs %}
{% tab title="First Tab" %}
```markup
  <div class="hero">
    <h1 contenteditable>🔥WOAH!</h1>
  </div>
```
{% endtab %}

{% tab title="Second Tab" %}
```css
  html {
    color: black;
    font-family: sans-serif;
  }

  body {
    margin: 0;
  }

  .hero {
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    color: black;
  }

  h1 {
    text-shadow: 10px 10px 0 rgba(0,0,0,1);
    font-size: 100px;
  }
```
{% endtab %}

{% tab title="" %}
```javascript
  const hero = document.querySelector('.hero');
  const text = hero.querySelector('h1');
  const walk = 100; // 50px

  function shadow(e) {
    const { offsetWidth: width, offsetHeight: height } = hero;
    let { offsetX: x, offsetY: y } = e;

    if (this !== e.target) {
      x = x + e.target.offsetLeft;
      y = y + e.target.offsetTop;
    }
  

console.log(width)
    const xWalk = Math.round((x / width * walk) - (walk / 2));
    const yWalk = Math.round((y / height * walk) - (walk / 2));

    text.style.textShadow = `
      ${xWalk}px ${yWalk}px 0 rgba(255,0,255,0.7),
      ${xWalk * -1}px ${yWalk}px 0 rgba(0,255,255,0.7),
      ${yWalk}px ${xWalk * -1}px 0 rgba(0,255,0,0.7),
      ${yWalk * -1}px ${xWalk}px 0 rgba(0,0,255,0.7)
    `;

  }

  hero.addEventListener('mousemove', shadow);
```
{% endtab %}
{% endtabs %}

mousemove 의 offset 값으로 이벤트를 주는 함수이다. 계산식을 모르고 있다면 하기 힘들겠다는 생각이좀 들었다.

**es6 구문**

```javascript
const { offsetWidth: width, offsetHeight: height } = hero;
let { offsetX: x, offsetY: y } = e;
/*
const width = hero.offsetWIdth;  
const height = hero.offsetHeight;

let x = e.offsetX
let y = e.offsetY  
*/
```

**contenteditable**

웹 브라우저 자체에서 text를 수정할수있게 해준다. 에디터로 활용할수있을거같다

