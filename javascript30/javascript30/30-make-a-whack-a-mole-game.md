# 30 - Make a Whack A Mole Game

{% tabs %}
{% tab title="HTML" %}
```markup
  <h1>Whack-a-mole! <span class="score">0</span></h1>
  <button onClick="startGame()">Start!</button>

  <div class="game">
    <div class="hole hole1">
      <div class="mole"></div>
    </div>
    <div class="hole hole2">
      <div class="mole"></div>
    </div>
    <div class="hole hole3">
      <div class="mole"></div>
    </div>
    <div class="hole hole4">
      <div class="mole"></div>
    </div>
    <div class="hole hole5">
      <div class="mole"></div>
    </div>
    <div class="hole hole6">
      <div class="mole"></div>
    </div>
  </div>
```
{% endtab %}

{% tab title="CSS" %}
```css
html {
  box-sizing: border-box;
  font-size: 10px;
  background: #ffc600;
}

*, *:before, *:after {
  box-sizing: inherit;
}

body {
  padding: 0;
  margin: 0;
  font-family: 'Amatic SC', cursive;
}

h1 {
  text-align: center;
  font-size: 10rem;
  line-height: 1;
  margin-bottom: 0;
}

.score {
  background: rgba(255,255,255,0.2);
  padding: 0 3rem;
  line-height: 1;
  border-radius: 1rem;
}

.game {
  width: 600px;
  height: 400px;
  display: flex;
  flex-wrap: wrap;
  margin: 0 auto;
}

.hole {
  flex: 1 0 33.33%;
  overflow: hidden;
  position: relative;
}

.hole:after {
  display: block;
  background: url(dirt.svg) bottom center no-repeat;
  background-size: contain;
  content: '';
  width: 100%;
  height:70px;
  position: absolute;
  z-index: 2;
  bottom: -30px;
}

.mole {
  background: url('mole.svg') bottom center no-repeat;
  background-size: 60%;
  position: absolute;
  top: 100%;
  width: 100%;
  height: 100%;
  transition:all 0.4s;
}

.hole.up .mole {
  top: 0;
}

```
{% endtab %}

{% tab title="JS" %}
```javascript
  const holes = document.querySelectorAll('.hole');
  const scoreBoard = document.querySelector('.score');
  const moles = document.querySelectorAll('.mole');
  let lastHole;
  let timeUp = false;
  let score = 0;

  function randomTime(min, max) {
    return Math.round(Math.random() * (max - min) + min);
  }

  function randomHole(holes) {
    const idx = Math.floor(Math.random() * holes.length);
    const hole = holes[idx];
    if (hole === lastHole) {
      console.log('Ah nah thats the same one bud');
      return randomHole(holes);
    }
    lastHole = hole;
    return hole;
  }

  function peep() {
    const time = randomTime(200, 1000);
    const hole = randomHole(holes);
    hole.classList.add('up');
    setTimeout(() => {
      hole.classList.remove('up');
      if (!timeUp) peep();
    }, time);
  }

  function startGame() {
    scoreBoard.textContent = 0;
    timeUp = false;
    score = 0;
    peep();
    setTimeout(() => timeUp = true, 10000)
  }

  function bonk(e) {
    if(!e.isTrusted) return; // cheater!
    score++;
    this.parentNode.classList.remove('up');
    scoreBoard.textContent = score;
  }

  moles.forEach(mole => mole.addEventListener('click', bonk));

```
{% endtab %}
{% endtabs %}
