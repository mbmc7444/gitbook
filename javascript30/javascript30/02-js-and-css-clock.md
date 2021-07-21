# 02 - JS and CSS Clock

{% tabs %}
{% tab title="HTML" %}
```markup
    <div class="clock">
      <div class="clock-face">
        <div class="hand hour-hand"></div>
        <div class="hand min-hand"></div>
        <div class="hand second-hand"></div>
      </div>
    </div>
```
{% endtab %}

{% tab title="CSS" %}
```css
 html {
      background: #018DED url(https://unsplash.it/1500/1000?image=881&blur=5);
      background-size: cover;
      font-family: 'helvetica neue';
      text-align: center;
      font-size: 10px;
    }

    body {
      margin: 0;
      font-size: 2rem;
      display: flex;
      flex: 1;
      min-height: 100vh;
      align-items: center;
    }

    .clock {
      width: 30rem;
      height: 30rem;
      border: 20px solid white;
      border-radius: 50%;
      margin: 50px auto;
      position: relative;
      padding: 2rem;
      box-shadow:
        0 0 0 4px rgba(0,0,0,0.1),
        inset 0 0 0 3px #EFEFEF,
        inset 0 0 10px black,
        0 0 10px rgba(0,0,0,0.2);
    }

    .clock-face {
      position: relative;
      width: 100%;
      height: 100%;
      transform: translateY(-3px); 
    }

    .hand {
      width: 50%;
      height: 6px;
      background: black;
      position: absolute;
      top: 50%;
      transform-origin: 100%;
      /* 시계 바늘의 기준점을 만들기위해서 작*/
      transform: rotate(90deg);
      transition: all 0.05s;
      transition-timing-function: cubic-bezier(0.1, 2.7, 0.58, 1);
    }
```
{% endtab %}

{% tab title="JS" %}
```javascript
 const secondHand = document.querySelector('.second-hand');
  const minsHand = document.querySelector('.min-hand');
  const hourHand = document.querySelector('.hour-hand');

  function setDate() {
    const now = new Date();
    
    const seconds = now.getSeconds();
    const secondsDegrees = ((seconds / 60) * 360) + 90;
    secondHand.style.transform = `rotate(${secondsDegrees}deg)`;

    const mins = now.getMinutes();
    const minsDegrees = ((mins / 60) * 360) + ((seconds/60)*6) + 90;
    minsHand.style.transform = `rotate(${minsDegrees}deg)`;

    const hour = now.getHours();
    const hourDegrees = ((hour / 12) * 360) + ((mins/60)*30) + 90;
    hourHand.style.transform = `rotate(${hourDegrees}deg)`;
  }

  setInterval(setDate, 1000);

  setDate();
```
{% endtab %}
{% endtabs %}

#### DATE

```javascript
const now = new Date(); 
//새로운 Date 객체를 생성 따로 매서드를 작성하지않으면 현재 날짜와 시간을 알수있다.
   
 const seconds = now.getSeconds(); //
 const mins = now.getMinutes(); //
 const hour = now.getHours(); //시
```

```javascript
const secondsDegrees = ((seconds / 60) * 360) + 90;
    /*
    ex 50초이면 50  / 60 = 0.83333333333
    0.83333333333 * 360 = 300 
    300 + 90 = 390도 
    90을 더하는 이유는 막대를 만들면 수평을 향하고 있기때문에 90도로 돌려야
    정확한 위치로 옮길수있다.
    */
```

#### setInterval\(function , time\)

time 값마다 함수를 실행할때 사용된다.

```javascript
setInterval(setDate, 1000);
```



