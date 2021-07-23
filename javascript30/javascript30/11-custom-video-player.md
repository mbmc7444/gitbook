# 11 - Custom Video Player

{% tabs %}
{% tab title="HTML" %}
```markup

   <div class="player">
     <video class="player__video viewer" src="652333414.mp4"></video>

     <div class="player__controls">
       <div class="progress">
        <div class="progress__filled"></div>
       </div>
       <button class="player__button toggle" title="Toggle Play">►</button>
       <input type="range" name="volume" class="player__slider" min="0" max="1" step="0.05" value="1">
       <input type="range" name="playbackRate" class="player__slider" min="0.5" max="2" step="0.1" value="1">
       <button data-skip="-10" class="player__button">« 10s</button>
       <button data-skip="25" class="player__button">25s »</button>
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

body {
  margin: 0;
  padding: 0;
  display: flex;
  background: #7A419B;
  min-height: 100vh;
  background: linear-gradient(135deg, #7c1599 0%,#921099 48%,#7e4ae8 100%);
  background-size: cover;
  align-items: center;
  justify-content: center;
}

.player {
  max-width: 750px;
  border: 5px solid rgba(0,0,0,0.2);
  box-shadow: 0 0 20px rgba(0,0,0,0.2);
  position: relative;
  font-size: 0;
  overflow: hidden;
}

/* This css is only applied when fullscreen is active. */
.player:fullscreen {
  max-width: none;
  width: 100%;
}

.player:-webkit-full-screen {
  max-width: none;
  width: 100%;
}

.player__video {
  width: 100%;
}

.player__button {
  background: none;
  border: 0;
  line-height: 1;
  color: white;
  text-align: center;
  outline: 0;
  padding: 0;
  cursor: pointer;
  max-width: 50px;
}

.player__button:focus {
  border-color: #ffc600;
}

.player__slider {
  width: 10px;
  height: 30px;
}

.player__controls {
  display: flex;
  position: absolute;
  bottom: 0;
  width: 100%;
  transform: translateY(100%) translateY(-5px);
  transition: all .3s;
  flex-wrap: wrap;
  background: rgba(0,0,0,0.1);
}

.player:hover .player__controls {
  transform: translateY(0);
}

.player:hover .progress {
  height: 15px;
}

.player__controls > * {
  flex: 1;
}

.progress {
  flex: 10;
  position: relative;
  display: flex;
  flex-basis: 100%;
  height: 5px;
  transition: height 0.3s;
  background: rgba(0,0,0,0.5);
  cursor: ew-resize;
}

.progress__filled {
  width: 50%;
  background: #ffc600;
  flex: 0;
  flex-basis: 50%;
}

/* unholy css to style input type="range" */

input[type=range] {
  -webkit-appearance: none;
  background: transparent;
  width: 100%;
  margin: 0 5px;
}

input[type=range]:focus {
  outline: none;
}

input[type=range]::-webkit-slider-runnable-track {
  width: 100%;
  height: 8.4px;
  cursor: pointer;
  box-shadow: 1px 1px 1px rgba(0, 0, 0, 0), 0 0 1px rgba(13, 13, 13, 0);
  background: rgba(255,255,255,0.8);
  border-radius: 1.3px;
  border: 0.2px solid rgba(1, 1, 1, 0);
}

input[type=range]::-webkit-slider-thumb {
  height: 15px;
  width: 15px;
  border-radius: 50px;
  background: #ffc600;
  cursor: pointer;
  -webkit-appearance: none;
  margin-top: -3.5px;
  box-shadow:0 0 2px rgba(0,0,0,0.2);
}

input[type=range]:focus::-webkit-slider-runnable-track {
  background: #bada55;
}

input[type=range]::-moz-range-track {
  width: 100%;
  height: 8.4px;
  cursor: pointer;
  box-shadow: 1px 1px 1px rgba(0, 0, 0, 0), 0 0 1px rgba(13, 13, 13, 0);
  background: #ffffff;
  border-radius: 1.3px;
  border: 0.2px solid rgba(1, 1, 1, 0);
}

input[type=range]::-moz-range-thumb {
  box-shadow: 0 0 0 rgba(0, 0, 0, 0), 0 0 0 rgba(13, 13, 13, 0);
  height: 15px;
  width: 15px;
  border-radius: 50px;
  background: #ffc600;
  cursor: pointer;
}

```
{% endtab %}

{% tab title="JS" %}
```javascript

const player = document.querySelector('.player');
const video = player.querySelector('.viewer');
const progress = player.querySelector('.progress');
const progressBar = player.querySelector('.progress__filled');
const toggle = player.querySelector('.toggle');
const skipButtons = player.querySelectorAll('[data-skip]');
const ranges = player.querySelectorAll('.player__slider');



function togglePlay() {
  const method = video.paused ? 'play' : 'pause';
  video[method]();
}

function updateButton() {
  const icon = this.paused ? '►' : '❚ ❚';
  console.log(icon);
  toggle.textContent = icon;
}

function skip() {
 video.currentTime += parseFloat(this.dataset.skip);
}

function handleRangeUpdate() {
  video[this.name] = this.value;
}

function handleProgress() {
  const percent = (video.currentTime / video.duration) * 100;
  progressBar.style.flexBasis = `${percent}%`;
}

function scrub(e) {
  const scrubTime = (e.offsetX / progress.offsetWidth) * video.duration;
  video.currentTime = scrubTime;
}


video.addEventListener('click', togglePlay);
video.addEventListener('play', updateButton);
video.addEventListener('pause', updateButton);
video.addEventListener('timeupdate', handleProgress);

toggle.addEventListener('click', togglePlay);
skipButtons.forEach(button => button.addEventListener('click', skip));
ranges.forEach(range => range.addEventListener('change', handleRangeUpdate));
ranges.forEach(range => range.addEventListener('mousemove', handleRangeUpdate));

let mousedown = false;
progress.addEventListener('click', scrub);
progress.addEventListener('mousemove', (e) => mousedown && scrub(e));
progress.addEventListener('mousedown', () => mousedown = true);
progress.addEventListener('mouseup', () => mousedown = false);



this.dataset.skip ==='plus' ? video.currentTime += skipPlus  : video.currentTime += skipMinus
```
{% endtab %}
{% endtabs %}

#### 재생하기

```javascript
function togglePlay() {
  const method = video.paused ? "play" : "pause";
  video[method]();
}
/* 
토글클래스로 토글하면 play , pause를 할수있다.
function togglePlay() {
  if (video.paused) {
    video.play();
  } else {
    video.pause();
  }
}
*/
```

#### 재생버튼

```javascript
function updateButton() {
  const icon = this.paused ? '►' : '❚ ❚';
  console.log(icon);
  toggle.textContent = icon;
}  // 재생버튼을 누르면 icon을 바꾸게 한다
```

#### 스

```javascript
function skip() {
 video.currentTime += parseFloat(this.dataset.skip);
}

/* 
video button 태그에 있는데 data-skip을 가져와서 더해주는 구문이다.
혼자 해보던중에 data-skip을 내장함수를 사용하지않고 각각 plus minus를 넣어
       <button data-skip="minus" class="player__button">« 10s</button>
       <button data-skip="plus" class="player__button">25s »</button>
       const skipPlus = 25;
       const skipMinus = -10;
       수값은 변수에 넣고 삼항연산자
this.dataset.skip ==='plus' ? video.currentTime += skipPlus  : video.currentTime += skipMinus
       로도 가능하다는걸 알았다. 물론 코드가 길어지기 때문에 이렇게 작성할 필요는 없을거같다.
*/
```

{% hint style="info" %}
**pareseFloat\(a\)**  a의 값\(string\) 을 수로 바꿔주는 자바스크립트 내장함수이다.

반대로 **pareseInt\(a\)** a의 값\(수\)을 문자열로 바꿔 줄 수도있다
{% endhint %}

\*\*\*\*

**볼 속도**

```javascript
function handleRangeUpdate() {
  video[this.name] = this.value;
}
// HTML태그에 type="range" 로 인한  value값으 조절 할수있다.


ranges.forEach((range) => range.addEventListener("change", handleRangeUpdate));
ranges.forEach((range) =>
  range.addEventListener("mousemove", handleRangeUpdate)
);

/*
change 값이 변경되면 그 변경된 값으로 함수가 실행되는것이고
mousemove는 해당 input을 누를 실시간으로 함수를 실 행 시키기 위함이다.
*/



```

**진행바**

```javascript
function scrub(e) {
  const scrubTime = (e.offsetX / progress.offsetWidth) * video.duration;
  video.currentTime = scrubTime;
} 
/*
 video 의 offsetx 의 값과 progress(진행바)넓이로 계산하는 코드
 영상의 currentTime progress 바를 움직였을때 해당 위치로 이동한다
 */
 
```

```javascript
function handleProgress() {
  const percent = (video.currentTime / video.duration) * 100;
  progressBar.style.flexBasis = `${percent}%`;
} //해당 video 객체의 길이와 영상길이를 계산해서 style에 넣는 작업이다.
```

```javascript
//이벤트

let mousedown = false;
/*
mousemove일때는 progress에 마우스를 가져다 놓으면 그즉시 currenttime 바뀌는데
이를막기위해 false 기본값이고 mousedown 했을시 true가 되게  하는것이다.
*/
progress.addEventListener("click", scrub);
progress.addEventListener("mousemove", (e) => mousedown && scrub(e));
// mousemove 를할때 mousedown이 되면 scrub 함수가 실행된다
progress.addEventListener("mousedown", () => (mousedown = true));
progress.addEventListener("mouseup", () => (mousedown = false));
```



#### fullscreen

[https://www.cckn.dev/js-ts/20210519-fullscreen/](https://www.cckn.dev/js-ts/20210519-fullscreen/)

