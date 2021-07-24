# 27 - JavaScript Interface Challenge: Click and Drag to Scroll

{% tabs %}
{% tab title="HTML" %}
```markup
  <div class="items">
    <div class="item item1">01</div>
    <div class="item item2">02</div>
    <div class="item item3">03</div>
    <div class="item item4">04</div>
    <div class="item item5">05</div>
    <div class="item item6">06</div>
    <div class="item item7">07</div>
    <div class="item item8">08</div>
    <div class="item item9">09</div>
    <div class="item item10">10</div>
    <div class="item item11">11</div>
    <div class="item item12">12</div>
    <div class="item item13">13</div>
    <div class="item item14">14</div>
    <div class="item item15">15</div>
    <div class="item item16">16</div>
    <div class="item item17">17</div>
    <div class="item item18">18</div>
    <div class="item item19">19</div>
    <div class="item item20">20</div>
    <div class="item item21">21</div>
    <div class="item item22">22</div>
    <div class="item item23">23</div>
    <div class="item item24">24</div>
    <div class="item item25">25</div>
  </div>
```
{% endtab %}

{% tab title="CSS" %}
```css
html {
  box-sizing: border-box;
  background: url('https://source.unsplash.com/NFs6dRTBgaM/2000x2000') fixed;
  background-size: cover;
}

*, *:before, *:after {
  box-sizing: inherit;
}

body {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: sans-serif;
  font-size: 20px;
  margin: 0;
}

.items {
  height: 800px;
  padding: 100px;
  width: 100%;
  border: 1px solid white;
  overflow-x: scroll;
  overflow-y: hidden;
  white-space: nowrap;
  user-select: none;
  cursor: pointer;
  transition: all 0.2s;
  transform: scale(0.98);
  will-change: transform;
  position: relative;
  background: rgba(255,255,255,0.1);
  font-size: 0;
  perspective: 500px;
}

.items.active {
  background: rgba(255,255,255,0.3);
  cursor: grabbing;
  cursor: -webkit-grabbing;
  transform: scale(1);
}

.item {
  width: 200px;
  height: calc(100% - 40px);
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-size: 80px;
  font-weight: 100;
  color: rgba(0,0,0,0.15);
  box-shadow: inset 0 0 0 10px rgba(0,0,0,0.15);
}

.item:nth-child(9n+1) { background: dodgerblue;}
.item:nth-child(9n+2) { background: goldenrod;}
.item:nth-child(9n+3) { background: paleturquoise;}
.item:nth-child(9n+4) { background: gold;}
.item:nth-child(9n+5) { background: cadetblue;}
.item:nth-child(9n+6) { background: tomato;}
.item:nth-child(9n+7) { background: lightcoral;}
.item:nth-child(9n+8) { background: darkslateblue;}
.item:nth-child(9n+9) { background: rebeccapurple;}

.item:nth-child(even) { transform: scaleX(1.31) rotateY(40deg); }
.item:nth-child(odd) { transform: scaleX(1.31) rotateY(-40deg); }

```
{% endtab %}

{% tab title="JS" %}
```javascript
  const slider = document.querySelector('.items');
  let isDown = false;
  let startX;
  let scrollLeft;

  slider.addEventListener('mousedown', (e) => {
    isDown = true;
    // 마우스 클릭했을시 true
    slider.classList.add('active');
    startX = e.pageX - slider.offsetLeft;
    scrollLeft = slider.scrollLeft;
  });

  slider.addEventListener('mouseleave', () => {
   // 마우스가 떠나면 다시 false
    isDown = false;
    slider.classList.remove('active');
  });

  slider.addEventListener('mouseup', () => {
  //해당 엘리먼트에 마우스를 가져다 놓으면 false
    isDown = false;
    slider.classList.remove('active');
  });

  slider.addEventListener('mousemove', (e) => {
  // isDown이 아닐때 즉 mousedown 상대로 움직일때
    if (!isDown) return;
    e.preventDefault();
    const x = e.pageX - slider.offsetLeft;
    const walk = (x - startX) * 3;
    slider.scrollLeft = scrollLeft - walk;
  });
  //

```
{% endtab %}
{% endtabs %}

