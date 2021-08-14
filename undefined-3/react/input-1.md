# input 심화

```jsx
import React, { useState } from 'react';
import logo from './logo.svg'
import './App.css';

function App() {
  let [글제목, 글제목변경] = useState(['남자 코트 추천', '강남 우동 맛집', '구로 음식 맛집']);
  let [따봉, 따봉변경] = useState(0);
  let [modal, modal변경] = useState(true);
  let [누른제목, 누른제목변경] = useState(0);
  let [입력값 , 입력값변경] = useState('');
  let posts = '강남 고기 맛집';

  function 제목변경() {
    let newArray = 글제목.map((newArrays) => newArrays)
    //     let newArray = [...글제목]
    newArray[0] = '여자코트 추천'
    글제목변경(newArray)
    
  }
  function 정렬() {
    let sortArray = 글제목.map((sortArrays) => sortArrays)
    글제목변경(sortArray.sort())
  }
  function 초기화() {
    let resetArray = 글제목.map((resetArrays) => resetArrays)
    resetArray = ['남자 코트 추천', '강남 우동 맛집', '구로 음식 맛집']
    글제목변경(resetArray)
    
  }
  function 인풋게시글추가(){
    // let inputArray =[...글제목];
    let inputArray = 글제목.map((inputArrays)=>inputArrays)
    inputArray.unshift(입력값)
    글제목변경(inputArray)
  
  }
 
  return (
    <div className="App">
      <div className="black-nav">
        <div>React Blog</div>
      </div>
      <button onClick={제목변경}>제목변경</button>
      <button onClick={정렬}>정렬</button>
      <button onClick={초기화}>초기화</button>
   {    
   글제목.map(function (list , i) {
    return (
      <div className="list" key={i}>
        <h3 onClick={()=>{누른제목변경(i)}}>{list}<span onClick={() => { 따봉변경(따봉 + 1) } } >👍</span> {따봉}</h3>
        <p>2월 17일 발행</p>
        <hr />
      </div>
    )
  })
    }
    <div className="inputbox">
      <input onChange={(e)=>{입력값변경(e.target.value)}} />
      <button onClick={인풋게시글추가}>저장</button>
    </div>
    {/* <input onChange={(e)=>{입력값변경(e.target.value)}} /> */}
      {/* <div className="list">
        <h3 onClick={modal함수}> {글제목[0]} <span onClick={() => { 따봉변경(따봉 + 1) }} >👍</span> {따봉}</h3>
        <p>2월 17일 발행</p>
        <hr />
      </div>
      <div className="list">
        <h3>{글제목[1]}</h3>
        <p>2월 17일 발행</p>
        <hr />
      </div>
      <div className="list">
        <h3>{글제목[2]}</h3>
        <p>2월 17일 발행</p>
        <hr />
      </div> */}
      <button onClick={()=>{누른제목변경(0)}}>버튼1</button>
      <button onClick={()=>{누른제목변경(1)}}>버튼2</button>
      <button onClick={()=>{누른제목변경(2)}}>버튼3</button>
      {
        modal === true
          ? <Modal 글제목 ={글제목} 누른제목 ={누른제목}></Modal>
          : null
      } 
      
      {/* <div className="modal">
        <h2>제목</h2>
        <p>날짜</p>
        <p>상세내용</p>
      </div> */}
    </div>
  );
}
 

function Modal(props) {
  return (
    <div className="modal">
      <h2 >제목{ props.글제목[props.누른제목]}</h2>
      <p>날짜</p>
      <p>상세내용</p>
    </div>
  )
}

export default App;


```

