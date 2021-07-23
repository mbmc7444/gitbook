# 10 - JS Checkbox Challenge!

{% tabs %}
{% tab title="HTML" %}
```markup
  <div class="inbox">
    <div class="item">
      <input type="checkbox">
      <p>This is an inbox layout.</p>
    </div>
    <div class="item">
      <input type="checkbox">
      <p>Check one item</p>
    </div>
    <div class="item">
      <input type="checkbox">
      <p>Hold down your Shift key</p>
    </div>
    <div class="item">
      <input type="checkbox">
      <p>Check a lower item</p>
    </div>
    <div class="item">
      <input type="checkbox">
      <p>Everything in between should also be set to checked</p>
    </div>
    <div class="item">
      <input type="checkbox">
      <p>Try do it without any libraries</p>
    </div>
    <div class="item">
      <input type="checkbox">
      <p>Just regular JavaScript</p>
    </div>
    <div class="item">
      <input type="checkbox">
      <p>Good Luck!</p>
    </div>
    <div class="item">
      <input type="checkbox">
      <p>Don't forget to tweet your result!</p>
    </div>
  </div>
```
{% endtab %}

{% tab title="CSS" %}
```css
 html {
      font-family: sans-serif;
      background: #ffc600;
    }

    .inbox {
      max-width: 400px;
      margin: 50px auto;
      background: white;
      border-radius: 5px;
      box-shadow: 10px 10px 0 rgba(0,0,0,0.1);
    }

    .item {
      display: flex;
      align-items: center;
      border-bottom: 1px solid #F1F1F1;
    }

    .item:last-child {
      border-bottom: 0;
    }


    input:checked + p {
      background: #F9F9F9;
      text-decoration: line-through;
    }

    input[type="checkbox"] {
      margin: 20px;
    }

    p {
      margin: 0;
      padding: 20px;
      transition: background 0.2s;
      flex: 1;
      font-family: 'helvetica neue';
      font-size: 20px;
      font-weight: 200;
      border-left: 1px solid #D1E2FF;
    }
```
{% endtab %}

{% tab title="JS" %}
```javascript
const checkboxes = document.querySelectorAll('.inbox input[type="checkbox"]');
let lastChecked;

function handleCheck(e) {
  let inBetween = false;
  if (e.shiftKey && this.checked) {
    checkboxes.forEach(checkbox => {
      if (checkbox === this || checkbox === lastChecked) {
        inBetween = !inBetween;
        console.log('Starting to check them in between!');
      }
      if (inBetween) {
        checkbox.checked = true;
      }
    });
  }

  lastChecked = this;
}

checkboxes.forEach(checkbox => checkbox.addEventListener('click', handleCheck));
```
{% endtab %}
{% endtabs %}

#### css

input중에 체크된 p만 line이 생기도록 하는 코드이다.

```css
input:checked + p {
  background: #f9f9f9;
  text-decoration: line-through;
}
```

#### js

각각의 체크박스  shift key 를 누르고 클릭을 했는지 안했는지 확인이 필요하다 그러기 위해서는 마지막 으로 클릭된 체크박스 객체를 변수로 지정해놓아야한다 \(lastChecked\). 그 후에는 선택한 체크박스 객체와 지금 클릭한 체크박스 객체 사이를 변수로 만들어주면 된다. \(inBetween\) 처음에는 inBetween을 false 로 초기화 시켜준후에 선택된 객체와 마지막에 선택된 객체 사이를 inBetween = true 로 업데이트 시켜줌으로써 true 인 객체들만 체크될수 있게 만든것이다

