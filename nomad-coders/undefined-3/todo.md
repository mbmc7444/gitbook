# todo 구현

JSON

* JSON.stringify\(\): 객체 ,배열 어떠한 코드건 string으로 만들어준다.
* JSON.parse\(\): string을 array로 만들어준다.

#### forEach\(\)

array안 item 들에게 반복문을 실행할때 사용

```javascript
array.forEach(sayHello)
  function sayHello(item){
        console.log(itme)
    }
/*
.forEach(item => {
     한번에 묶어서하는 방법이있다.
     이안의 함수가 sayHello()와 같다
 });
*/
```

```javascript
const toDoForm = document.getElementById("todo-form");
const toDoInput = toDoForm.querySelector("input");
const toDoList = document.getElementById("todo-list");
const TODOS_KEY = "todos"



let toDos = [];
// localStorage 배열로 저장 되지 않는다.

function saveToDos(){
    localStorage.setItem("todos", JSOAN.stingify(toDos))
}
function deleteToDo(event){
  //어떤 버튼을 눌러서 삭제하는지 모르기때문에 console.dir(event.target.parentElement) 를하면각각의 타겟을 찾을수있다. 
    const deleteLi = event.target.parntElement;
    deleteLi.remove();
}


function paintToDo(newTodo){
    const li = document.createElement("li")
    const span = document.createElement("span")
    span.innterText = newTodo;
    const button = document.createElement("button")
    button.innerText ="X"
    button.addEventListener("click", deleteToDo)
    li.appendChild(span)
    li.appendChild(button)
    toDoList.appendChild(li)
}


function handleToDoSubmit(event){
event.preventDefault();
const newTodo  = toDoInput.value; 
toDoInput.value = ""; 
//시작지점이 다르기때문에 input value 를 없앴다고 해도 newTodo 값이 바뀌지않는다
toDos.push(newTodo);
paintToDo(newTodo);
saveToDos(); 
}

toDoForm.addEventListener("submit", handleToDoSubmit)



const savedToDo =  localStorage.getItem(TODOS_KEY)

if(saveToDos !== null){ //null 이 아닐때
    const parseToDos = JSON.parse(saveToDos); 
    toDos = parseToDos;
    parseToDos.forEach(paintToDo);
    /*
    이미 paintToDo에서 모든걸 만들고 추가하기때문에 
    각각을 JSON.parse(saveToDos)해주면 된다.
    
    */
}


```

{% hint style="info" %}
toDos = parseToDos 

이 구문을 추가시키지않으면 ,  toDos.push\(newTodo\) 로인해  

빈 let toDos 에 추가만하고 저장되지 않는다. 

기존에 있던 parseToDos 들을 toDos에 넣는 과정이다.
{% endhint %}

