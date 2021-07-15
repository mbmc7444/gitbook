# Event

#### addEventListener

{% tabs %}
{% tab title="click" %}
```javascript
const title = document.querySelector(".hello h1");

function handleTitleClick(){
    console.log("title was clicked!");
}

title.addEventListener("click", handleTitleClick); 
// title 클릭하면 함수를 실행시켜준다
```
{% endtab %}

{% tab title="mouseenter" %}
```javascript
const title = document.querySelector(".hello h1");

function handleMouseEnter(){
    console.log("mouse is here!")
}
title.addEventListener("mouseenter",handleMouseEnter)
// title에 마우스를 가져다 대면 실행된
```
{% endtab %}

{% tab title="mouseleave" %}
```javascript
const title = document.querySelector(".hello h1");

function handleMouseLeave(){
    console.log("mouse is gone!")
}
title.addEventListener("mouseleave",handleMouseLeave)
//타이틀에 마우스를 떠나면 실행된
```
{% endtab %}
{% endtabs %}

* resize : 사용자가 윈도우창의 크기를 바꿨을때,
* copy : 사용자가 해당 variable을 copy 했을,
* offline: 사용자의 인터넷이 끊기게되면,
* online: 사용자의 인터넷이 연결되면,

#### onEvent

```javascript
title.onclick = handleTitleClick;
title.onmouseenter = handleMouseEnter;
title.onmouseleave = handleMouseLeave;
// 이런식으로도 이벤트를 만들 수 있지만 잘사용하지 않는다 
```

