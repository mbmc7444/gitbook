# CSS in Javascript

```javascript
const h1 = document.querySelector("div.hello:frist-child h1");

function handleTitleClick(){
    if(h1.style.color ==="blue"){
        h1.style.color ="tomato"
    } else{
    h1.style.color = "blue"
    }
}

h1.addEventListener("click", handleTitleClick);
```

