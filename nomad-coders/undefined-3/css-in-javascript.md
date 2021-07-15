# CSS in Javascript

```javascript
const h1 = document.querySelector("div.hello:frist-child h1");

function handleTitleClick(){
  const currentColor = h1.style.color;
  let newColor;
    if(currentColor ==="blue"){ //h1의 글자색이 파랑이면
        newColor ="tomato"; // newColor = 토마토색
    } else{
        newColor = "blue"; // h1의 글작색이 파랑이 아니 newColor = 파랑
    }
    h1.style.color = newColor; // 마지막으로 h1 색을 newColor로 바꿔
}

h1.addEventListener("click", handleTitleClick);
```



