# 03 - CSS Variables

{% tabs %}
{% tab title="HTML" %}
```markup
 <h2>Update CSS Variables with <span class='hl'>JS</span></h2>

  <div class="controls">
    <label for="spacing">Spacing:</label>
    <input id="spacing" type="range" name="spacing" min="10" max="200" value="10" data-sizing="px">

    <label for="blur">Blur:</label>
    <input id="blur" type="range" name="blur" min="0" max="25" value="10" data-sizing="px">

    <label for="base">Base Color</label>
    <input id="base" type="color" name="base" value="#ffc600">
  </div>

  <img src="https://source.unsplash.com/7bwQXzbF6KE/800x500">

```
{% endtab %}

{% tab title="CSS" %}
```css
    :root {
      --base: #ffc600;
      --spacing: 10px;
      --blur: 10px;
    }

    img {
      padding: var(--spacing);
      background: var(--base);
      filter: blur(var(--blur));
    }

    .hl {
      color: var(--base);
    }
    
    
        body {
      text-align: center;
      background: #193549;
      color: white;
      font-family: 'helvetica neue', sans-serif;
      font-weight: 100;
      font-size: 50px;
    }

    .controls {
      margin-bottom: 50px;
    }

    input {
      width: 100px;
    }
```
{% endtab %}

{% tab title="JS" %}
```javascript
    const inputs = document.querySelectorAll('.controls input');

    function handleUpdate() {
      const suffix = this.dataset.sizing || '';
      document.documentElement.style.setProperty(`--${this.name}`, this.value + suffix);
    }

    inputs.forEach(input => input.addEventListener('change', handleUpdate));
    inputs.forEach(input => input.addEventListener('mousemove', handleUpdate));
```
{% endtab %}
{% endtabs %}

#### ::root

css값을 변수로 저장할수있다 . 이때 :root 로 사용할경우 html 전역에 접근할수있다.

```css
     :root {
      --base: #ffc600;
       --spacing: 10px;
      --blur: 10px;
      /*--지정속성명: 값; */
    }

    img {
      padding: var(--spacing);
      background: var(--base);
      filter: blur(var(--blur));
        /* 속성: var(--지정속성) */
    }
```

[http://tcpschool.com/css/css\_selector\_pseudoClass](http://tcpschool.com/css/css_selector_pseudoClass)

#### dataset

작성자가 임의로\(따로 설명이 필요한 또는 정보를 담고싶은\) 작성하여 javascript로 가져올때 사용

```javascript
const suffix = this.dataset.sizing || '';
// 해상 값의 dataset의 sizing 이 '' 일때 (undefined)
```

{% hint style="info" %}
css에서는 content: attr\(data-parent\); 로 불러올수있다
{% endhint %}

#### css제

* setProperty \(속성이름, 값\) : css 값을 변경할때사용
* getPropertyValue\(속성이\): css 값을 가져올때 사용
* removeProperty\(속성이름\) :css 값을 삭제할때 사용

#### documentElemnt

document에서 html요소를 반환

```javascript
   document.documentElement.style.setProperty(`--${this.name}`, this.value + suffix);
   //html 요소스타일을 이벤트를 주고싶은 해당 이름의 값을 가져와서 바꾼값으로 변경한다
```

#### change mousemove

```javascript
inputs.forEach(input => input.addEventListener('change', handleUpdate));
// inputs 들 값이 변경되면 핸들함수가 실행
inputs.forEach(input => input.addEventListener('mousemove', handleUpdate));
/*
inputs에 마우스를 움직일때 함수가 실행
이작업을 하는이유는 해당 인풋을 잡고 위치만 옮겨도 함수이벤트가 실행되게 하기위함이다.
*/
```



