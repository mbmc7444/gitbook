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

document 안에 존재하는 함수로 document 안에 존재하는 해당 element를 css형태로 불러올 수 있다.

```javascript
<div class="hello">
    <h1>
```

