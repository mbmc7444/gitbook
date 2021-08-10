# state

react에서 데이터를 쉽게 저장할수있는 방법 중 하나이다.

```jsx
import React, { useState } from 'react';

```

```jsx
import logo from './logo.svg'
import './App.css';


function App() {
  let posts = '강남 고기 맛집';
  let [글제목, 글제목변경] = useState('남자 코트 추천' , '강남 우동 맛');

  return (
   <div className="App">
      <div className="black-nav">
        <div>React Blog</div>
      </div>
      <div className="list">
        <h3>{ 글제목[1] }</h3>
        <p>2월 17일 발행</p>
        <hr/>
      </div>
    </div>
  );
}
export default App;

```

{% hint style="info" %}
ES6 destructuring 문법

let \[a,b\] = useState\('남자 코트 추천'\); 

a 는 남자코트 추천이라는 데이터가 들어가며

b는 그값을 변경할수 있게 도와주는 함수가 들어게된다.
{% endhint %}

#### 왜 굳이 state를 사용할까?

state안에 저장된 값들이 변경이되면 웹 브라우저가 재 렌더링이 되게된다. 새로고침을 하지않아도 된



