# todo 구현

JSON

* JSON.stringify\(\): 객체 ,배열 어떠한 코드건 string으로 만들어준다.
* JSON.parse\(\): string을 array로 만들어준다.

#### forEach\(\)

array안 item 들에게 반복문을 실행할때 사용

#### filter

주어진 함수의 테스트를 통과하는 모든 요소를 모아 새로운 배열로 반환

```javascript
const arr = [1,2,3,4,5]
const sexyFilter(item){return item !==3}
const newArr = arr.filter(sexyFilter);
// true 된것만 통과 3이 아닌것만 리턴한다
// arr = 1,2,3,4,5  newArr = 1,2,4,5 

```

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
// localStorage 배열x
// JSAN.stringify() 객체는 배열이든 어떠한 javascript 코드건 string으로 만들어준다
// JSAN.parse() string array 로 만들어좀

function saveToDos(){
    localStorage.setItem("todos", JSON.stringify(toDos))
}
function deleteToDo(event){
  //어떤 버튼을 눌러서 삭제하는지 모르기때문에 console.dir(event.target.parentElement) 를하면각각의 타겟을 찾을수있다. 
    const deleteLi = event.target.parentElement;
    deleteLi.remove();
    const sexyFilter = (arg) => {
        return toDos.filter((todo) => todo.id !== parseInt(arg.id));
    };
        //deleteLi.id  string 이기때문에 number 로 바꿔줘야한다
}


function paintToDo(newTodo){
    const li = document.createElement("li")
    li.id = newTodo.id
    const span = document.createElement("span")
    span.innterText = newTodo.text;
    const button = document.createElement("button")
    button.innerText ="X"
    button.addEventListener("click", deleteToDo)
    li.appendChild(span)
    li.appendChild(button)
    toDoList.appendChild(li)
}


function handleToDoSubmit(event){
event.preventDefault();
const newTodo  = toDoInput.value; // 
toDoInput.value = ""; //시작지점이 다르기때문에 input value 를 없앴다고 해도 newTodo 값이 바뀌지않는다
const newTodoObj = {
    text: newTodo,
    id:Date.now()
}

toDos.push(newTodoObj);
paintToDo(newTodoObj);
saveToDos(); 
}

toDoForm.addEventListener("submit", handleToDoSubmit)


const savedToDos =  localStorage.getItem(TODOS_KEY)

if(savedToDos !== null){ //null 이 아닐때
    const parseToDos = JSON.parse(savedToDos); 
    //javascript 는 array의 각각의 item 에대해 function 을 실행시켜준다 .
    toDos = parseToDos;
    parseToDos.forEach(paintToDo);
}
 


```

{% hint style="info" %}
toDos = parseToDos 

이 구문을 추가시키지않으면 ,  toDos.push\(newTodo\) 로인해  

빈 let toDos 에 추가만하고 저장되지 않는다. 

기존에 있던 parseToDos 들을 toDos에 넣는 과정이다.
{% endhint %}

####  



