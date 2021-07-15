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

위의 코드 처럼 작성해도 무관하지만 css는 css 파일로 분리해서 관리 하는것이 좋다.

```css
/* css */
.clicked{
    color:tomato;
}
.sexy-font{
 font-family: 'Noto Sans KR', sans-serif;
}
```

```javascript
/* js */
const h1 = document.querySelector("div.hello:fist-child h1")

function handleTitleClick(){
    const clickedClass = "clicked sexy-font" 
    // className 직업 작성하면 여러곳에서 오타가 발생할수도있고 위험하다.
    if(h1.className === clickedClass){
        h1.className = "";
    }else{
        h1.className = clickedClass ;
    }
}
h1.addEventListener("click", handleTitleClick);

//같은 결과라도 간결한 코드가 작성된다. 
```

#### 코드 개선

className 자체를 교체하는건 심각한 오류가 생길수 도 있다.

classList.contains\(\) 

* class 안에 존재 유무를 판단하고
* 해당 class를 교체 \(삭제\) 하지않고 추가 한다.

```javascript
const h1 = document.querySelector("div.hello:fist-child h1")

function handleTitleClick(){
    const clickedClass = "clicked";
    if(h1.classList.contains(clickedClass){
        h1.classList.remove(clickedClass)
    }else{
        h1.classList.add(clickedClass)
    }
}
h1.addEventListener("click", handleTitleClick);
```

toogle\(\)

* class 안에 존재 유무를 판단하고
* 해당 class를 교체 \(삭제\) 하지않고 추가 한다.
* if문을 대신 해준다.

```javascript
const h1 = document.querySelector("div.hello:fist-child h1")

function handleTitleClick(){
    h1.classList.toggle("clicked") // if문과 유사
}
h1.addEventListener("click", handleTitleClick);
```

