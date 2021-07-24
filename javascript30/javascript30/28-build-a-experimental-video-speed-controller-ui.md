# 28 - Build a Experimental Video Speed Controller UI

{% tabs %}
{% tab title="HTML" %}
```markup
<div class="wrapper">
    <video class="flex" width="765" height="430" src="http://clips.vorwaerts-gmbh.de/VfE_html5.mp4" loop controls></video>
    <div class="speed">
      <div class="speed-bar">1×</div>
    </div>
  </div>
```
{% endtab %}

{% tab title="CSS" %}
```css
body {
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background: #4C4C4C url('https://unsplash.it/1500/900?image=1021');
  background-size: cover;
  font-family: sans-serif;
}

.wrapper {
  width: 850px;
  display: flex;
}

video {
  box-shadow: 0 0 1px 3px rgba(0,0,0,0.1);
}

.speed {
  background: #efefef;
  flex: 1;
  display: flex;
  align-items: flex-start;
  margin: 10px;
  border-radius: 50px;
  box-shadow: 0 0 1px 3px rgba(0,0,0,0.1);
  overflow: hidden;
}

.speed-bar {
  width: 100%;
  background: linear-gradient(-170deg, #2376ae 0%, #c16ecf 100%);
  text-shadow: 1px 1px 0 rgba(0,0,0,0.2);
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2px;
  color: white;
  height: 16.3%;
}

```
{% endtab %}

{% tab title="JS" %}
```javascript
 const speed = document.querySelector('.speed');
  const bar = speed.querySelector('.speed-bar');
  const video = document.querySelector('.flex');

  function handleMove(e) {
      const y = e.pageY - this.offsetTop;
      const percent = y / this.offsetHeight;
      const min = 0.4;
      const max = 4;
      const height = Math.round(percent * 100) + '%';
      const playbackRate = percent * (max - min) + min;
      bar.style.height = height;
      bar.textContent = playbackRate.toFixed(2) + '×';
      video.playbackRate = playbackRate;
    }

  speed.addEventListener('mousemove', handleMove);
```
{% endtab %}
{% endtabs %}

bar에 마우스를 가져다 놓으면 이벤트가 발생할수있도록 addEventListener 을 만들어준다.

e.pageY - this.offsetTop 을 하면 막대기 안에서의 위치값을 구할수있다 .

퍼센트값으로 만들어 속도의 비율을 계산해준다

**toFixed\(\)**

소수의 자리수의 길이를 제한함

