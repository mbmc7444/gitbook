# 25 - Event Capture, Propagation, Bubbling and Once

{% tabs %}
{% tab title="HTML" %}
```markup
  <div class="one">
    <div class="two">
      <div class="three">
      </div>
    </div>
  </div>

```
{% endtab %}

{% tab title="CSS" %}
```css
 html {
    box-sizing: border-box;
  }
  
  *, *:before, *:after { 
    box-sizing: inherit; 
  }

  div {
    width: 100%;
    padding: 100px;
  }

  .one {
    background: thistle;
  }

  .two {
    background: mistyrose;
  }

  .three {
    background: coral;
  }
</style>

<button></button>
```
{% endtab %}

{% tab title="JS" %}
```javascript
 const divs = document.querySelectorAll('div');
  const button = document.querySelector('button');

  function logText(e) {
    console.log(this.classList.value);
  }

  divs.forEach(div => div.addEventListener('click', logText, {
    capture: false,
    once: true
  }));

  button.addEventListener('click', () => {
    console.log('Click!!!');
  }, {
    once: true
  });
```
{% endtab %}
{% endtabs %}

e.stopPropagation\(\);

상위 div안에 하위 div들에게 이벤트를 주었을경우 상위 div에게도 이벤트가 생기는 경우가 있다 이것이 bubbling 이라고 하는데 이것을 막을때 사용한다.

element.addEventListener\('click', doSomething, false\);

addEventListener 는 3개의 인자를 받는데 하나는 어떤 **이벤트를 줄것**인지 이고 두번째는 **함수** 마지막으로는 **useCapture** 이라 불리는 불린값으로, 이벤트 버블링이나 캡쳐링을 사용할것인지 나타낸다.

default 값이 false 이기 때문에, 단순히 사용했다면 버블링을 통해 이벤트를 전파한다.

* **capture** - 불린. 위에 언급된 useCapture 와 동일한 인자.
* **once** - 불린. true 면 이벤트가 딱 한번만 발생
* **passive** - 불린. true 면 콜백 함수내부에 preventDefault\(\) 가 있다 하더라도 실행되지않음.

\*\*\*\*

\*\*\*\*

\*\*\*\*

  


