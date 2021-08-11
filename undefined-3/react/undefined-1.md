# 반복문

```jsx
import React, { useState } from 'react';
import logo from './logo.svg'
import './App.css';

function App() {
  let [글제목, 글제목변경] = useState(['남자 코트 추천', '강남 우동 맛집', '구로 음식 맛집']);
  let [따봉, 따봉변경] = useState(0);
  let [modal, modal변경] = useState(false);

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
    modal변경(false)
  }
  function modal함수() {
    if (modal === true) {
      modal변경(false)
    } else {
      modal변경(true)
    }
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
   글제목.map(function (list) {
    return (
      <div className="list">
        <h3 onClick={modal함수}>{list}<span onClick={() => { 따봉변경(따봉 + 1) }} >👍</span> {따봉}</h3>
        <p>2월 17일 발행</p>
        <hr />
      </div>
    )
  })
    }
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
      {
        modal === true
          ? <Modal></Modal>
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


function Modal() {
  return (
    <div className="modal">
      <h2>제목</h2>
      <p>날짜</p>
      <p>상세내용</p>
    </div>
  )
}

export default App;
```

구현은 가능하지만 따봉을 눌렀을때, 3개를 공유하고 있기때문에 모든 따봉의 값이 오른다 계속해봤는데 아직은 잘모르겠다. 알게되면 작성해야지

또 App 자체에 map을 넣었는데 혹시 function을 만들고 그함수를 넣으면 함수만으로 list를 만들수있지 않을까 생각해봤는데 잘안됐다. 아마 이것도 component 개념으로 props가 필요하지않을까 생각된다. 추후에 수정해야겠다 

