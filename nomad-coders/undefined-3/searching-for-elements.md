# Searching For Elements

#### getElementById

document 안에 존재하는 함수로 document 안에 존재하는 해당 id의 element를 불러올수 있다.

* className
* innerText
* autofocus
* etc

```javascript
<h1 autofocus class="hello" id="title"> 안녕하세요 </h1>

const title = document.getElementById("title");

title.className ="helllllo";
title.innerText = "반갑습니다."

console.log(title.className) // helllllo 
console.log(title.innerText) // 반갑습니다.
```

{% hint style="info" %}
html 안의 값들을 javascript로 언제든지 확인,추가,변경,삭제가 가능하다.
{% endhint %}

#### getElementByClassName

document 안에 존재하는 함수로 document 안에 존재하는 해당 class의 element를 불러올 수 있다.

#### querySelector , querySelectorAll

document 안에 존재하는 함수로 document 안에 존재하는 해당 element를 css형태로 불러올 수 있다

```markup
<div class="hello">
    <h1>안녕하세요1</h1>
</div>
<div class="hello">
    <h1>안녕하세요2</h1>
</div>
<div class="hello">
    <h1>안녕하세요3</h1>
</div>

```

```javascript
const title = document.querySelector(".hello h1");
console.log(title) // <h1>안녕하세요1</h1>

const titleAll = document.querySelector(".hello h1");
console.log(titleAll) // NodeList(3) [h1,h1,h1] //복수의 element를 array로 불러온
```

{% hint style="info" %}
querySelector 로 element를 불러올경우 태그 자체로 불러와 지기때문에 모든 Object를 보고싶다면 console.dir\(".hello h1"\) 를하면 된다
{% endhint %}

```javascript
title.style.color ="blue" // 타이틀의 글자색 바꿀 수있다
```

