# 08 - Fun with HTML5 Canvas

{% tabs %}
{% tab title="HTML" %}
```markup
<canvas id="draw" width="800" height="800"></canvas>
```
{% endtab %}

{% tab title="JS" %}
```javascript
const canvas = document.querySelector('#draw');
const ctx = canvas.getContext('2d');
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;
ctx.strokeStyle = '#BADA55';
ctx.lineJoin = 'round';
ctx.lineCap = 'round';
ctx.lineWidth = 100;
// ctx.globalCompositeOperation = 'multiply';

let isDrawing = false;
let lastX = 0;
let lastY = 0;
let hue = 0;
let direction = true;

function draw(e) {
  if (!isDrawing) return;
  console.log(e);
  ctx.strokeStyle = `hsl(${hue}, 100%, 50%)`;
  ctx.beginPath();
  // start from
  ctx.moveTo(lastX, lastY);
  // go to
  ctx.lineTo(e.offsetX, e.offsetY);
  ctx.stroke();
  [lastX, lastY] = [e.offsetX, e.offsetY];

  hue++;
  if (hue >= 360) {
    hue = 0;
  }
  if (ctx.lineWidth >= 100 || ctx.lineWidth <= 1) {
    direction = !direction;
  }

  if(direction) {
    ctx.lineWidth++;
  } else {
    ctx.lineWidth--;
  }

}

canvas.addEventListener('mousedown', (e) => {
  isDrawing = true;
  [lastX, lastY] = [e.offsetX, e.offsetY];
});


canvas.addEventListener('mousemove', draw);
canvas.addEventListener('mouseup', () => isDrawing = false);
canvas.addEventListener('mouseout', () => isDrawing = false);
```
{% endtab %}
{% endtabs %}

#### canvas

&lt;canvas&gt; 요소는 고정된 크기의 드로잉 영역을 생성하며, 그 영역은 보여질 컨텐츠를 생성하고 다루게될 두가지 이상의 렌더링 컨텍스트를 노출시킨다.\(2D, 3D\)

```javascript
const canvas = document.querySelector('#draw');
const ctx = canvas.getContext('2d');
// getContext() 메소드를 호출하여 랜더링 컨텍스트와 그리기 함수들을 사용할 수 있다. 
```

```javascript
let isDrawing = false; 
// 마우스를 누르고 땔때 false 값과 true을 변경하면서 이벤트를 주기위함  
let lastX = 0;
// 마우스를 눌렀을때 그림을 그리기 시작하는 구
let lastY = 0;
//  마우스를 땠때 그림이 끝나는 구간
let hue = 0;
// 색상 조절
let direction = true;
//linewidth 와 색을 조절할때 사용
ctx.strokeStyle = '#BADA55';
// 선
ctx.lineJoin = 'round';
//선모
ctx.lineCap = 'round';
//선끝 모
ctx.lineWidth = 100;
//선 두께

```

색상

[https://mothereffinghsl.com/](https://mothereffinghsl.com/)

