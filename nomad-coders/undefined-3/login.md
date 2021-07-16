# Login 구현

```markup
    <div id="login-form">
        <input type="text">
        <button>login</button>
    </div>
```

```javascript
const loginFrom = document.getElementById("login-form")
const loginInput = loginFrom.querySelector("input")
const loginButton = loginFrom.querySelector("button")
/*
document 에서 찾는것이 아닌  
loginFrom에서 찾으면
좀더 정밀조사가 가능해진다
*/

```

다른방법

```javascript
const loginInput = document.querySelector("#login-form input")
const loginButton = document.querySelector("#login-form button")
```

#### Input Value

```javascript
loginInput.vaule // input 안의 값을 구할수있다.
```

#### preventDefault\(\)  

ㄹ

```javascript
브라우저의 기본 기능을 막을수있다.
```

```javascript
function onLoginSubmit(event){
event.preventDefault() 	 
/* 
input의 경우 submit의 새로고침 기능을 막을수있다.
*/
const username = loginInput.value;
} 
loginForm.addEventListener(“submit” , onLoginSubmit)
```

#### 백틱기호\(\`\`\)

string 변수를 하나로 합칠때 사용

* ${변수}
* \`\` 기호를 넣어야한다.

```javascript
greeting.innerText = “Hello ” + username; 
greeting.innerText = `Hello ${username}`
//변수를 좀더 직관적으로 알수있다.
```

#### Saving Username

input에 username 을 넣으면 그값을 기억해야 로그인을 구현할수있다. 그러나 서버가 없기때문에 우리는 그걸 대신해주기 위해 함수에서 기본적으로 만들어둔 **localStorage**를  사용할것이다.

* localStorage.selItem\("key", "value"\): 데이터 저장
* localStorage.removeItem\("key"\) : 데이터 삭제
* localStorage.getItem\("key"\): 데이터 불러오기

```markup
    <form id="login-form">
        <input type="text">
        <button>login</button>
    </form>
    <h1 id="greeting" class="hidden"></h1>
```

```javascript
const loginInput = document.querySelector("#login-form input")
const loginButton = document.querySelector("#login-form button")
const greeting = document.querySelector(“#greeting”)
const HIDDEN_CLASSNAME =“hidden” 
/*
일반적인 관습인데 string만 포함된 변수는 대문자로 표기하고 
string을 저장하고 싶을때 사용한다 안써도 무관
*/

function onLoginSubmit(event){
    event.preventDefault() 	
    const username = loginInput.value;
    loginForm.classList.add(HIDDEN_CLASSNAME);
    locatStorage.setItem(“username”, username)
    greeting.innerText = `Hello ${username}`
    greeting.classList.remove(HIDDEN_CLASSNAME)
} 

loginForm.addEventListener("submit" onLoginSubmt)

```



