# state 변경

```jsx
/* eslint-disable */

import React, { useState } from 'react';
import logo from './logo.svg'
import './App.css';

function App() {
  let [글제목, 글제목변경] = useState(['남자 코트 추천' , '강남 우동 맛집' , '구로 음식 맛집']);
  let [ 따봉, 따봉변경 ] = useState(0); 
  let posts = '강남 고기 맛집';
  function 제목변경(){
    let newArray = 글제목.map((newArrays)=>newArrays)
    //     let newArray = [...글제목]
    newArray[0] = '여자코트 추천'
    글제목변경(newArray.sort())
  }
  return (
   <div className="App">
      <div className="black-nav">
        <div>React Blog</div>
      </div>
      <button onClick={제목변경}>버튼</button>
      <div className="list">
      <h3> { 글제목[0] } <span onClick={ ()=>{ 따봉변경(따봉 + 1) } } >👍</span> { 따봉 }</h3>
        <p>2월 17일 발행</p>
        <hr/>
      </div>
      <div className="list">
        <h3>{ 글제목[1] }</h3>
        <p>2월 17일 발행</p>
        <hr/>
      </div>
      <div className="list">
        <h3>{ 글제목[2] }</h3>
        <p>2월 17일 발행</p>
        <hr/>
      </div>
    </div>
  );
}
export default App;

```

{% hint style="info" %}
제목변경 함수안에서 let newArray = 글제목; 으로 할 경우 별개의 array가 되는것이아닌 하나의 값을 공유한다. 따라서 spread 문법으로 복사를 하거나 map 으로 새로운 함수를 만들어서 값을 변경 하면된다
{% endhint %}

```jsx
import React, { useState } from 'react';
import logo from './logo.svg'
import './App.css';

function App() {
  let [글제목, 글제목변경] = useState(['남자 코트 추천' , '강남 우동 맛집' , '구로 음식 맛집']);
  let [ 따봉, 따봉변경 ] = useState(0); 

  let posts = '강남 고기 맛집';

  function 제목변경(){
    let newArray = 글제목.map((newArrays)=>newArrays)
    //     let newArray = [...글제목]
    newArray[0] = '여자코트 추천'
    글제목변경(newArray)
  }
  function 정렬(){
    let sortArray = 글제목.map((sortArrays)=>sortArrays)
    글제목변경(sortArray.sort())
  }
  function 초기화(){
    let resetArray = 글제목.map((resetArrays)=>resetArrays)
    resetArray = ['남자 코트 추천' , '강남 우동 맛집' , '구로 음식 맛집']
    글제목변경(resetArray)
  }
  return (
   <div className="App">
      <div className="black-nav">
        <div>React Blog</div>
      </div>
      <button onClick={제목변경}>제목변경</button>
      <button onClick={정렬}>정렬</button>
      <button onClick={초기화}>초기화</button>
      <div className="list">
      <h3> { 글제목[0] } <span onClick={ ()=>{ 따봉변경(따봉 + 1) } } >👍</span> { 따봉 }</h3>
        <p>2월 17일 발행</p>
        <hr/>
      </div>
      <div className="list">
        <h3>{ 글제목[1] }</h3>
        <p>2월 17일 발행</p>
        <hr/>
      </div>
      <div className="list">
        <h3>{ 글제목[2] }</h3>
        <p>2월 17일 발행</p>
        <hr/>
      </div>
    </div>
  );
}
export default App;
```

