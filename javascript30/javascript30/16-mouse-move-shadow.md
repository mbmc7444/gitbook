# 16 - Mouse Move Shadow

{% tabs %}
{% tab title="First Tab" %}
```markup
  <div class="hero">
    <h1 contenteditable>๐ฅWOAH!</h1>
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

mousemove ์ offset ๊ฐ์ผ๋ก ์ด๋ฒคํธ๋ฅผ ์ฃผ๋ ํจ์์ด๋ค. ๊ณ์ฐ์์ ๋ชจ๋ฅด๊ณ  ์๋ค๋ฉด ํ๊ธฐ ํ๋ค๊ฒ ๋ค๋ ์๊ฐ์ด์ข ๋ค์๋ค.

**es6 ๊ตฌ๋ฌธ**

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

์น ๋ธ๋ผ์ฐ์  ์์ฒด์์ text๋ฅผ ์์ ํ ์์๊ฒ ํด์ค๋ค. ์๋ํฐ๋ก ํ์ฉํ ์์์๊ฑฐ๊ฐ๋ค

