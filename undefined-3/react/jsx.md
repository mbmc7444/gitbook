# JSX

JSX 란 리엑트에서 사용되는 문법으로 html , 문자열도아닌 javascript 문법이다.

필수는 아니지만 ui관련 작업을 할때 시각적으로 더 도움이 된다.

또한 데이터 바인딩이 쉽다.

{% hint style="info" %}
데이터 바인딩이란 간단하게 서버에서 값을 가져오고 그값을 브라우저에 출력하는것을 말한다.
{% endhint %}

```jsx
import React from 'react';
import logo from './logo.svg'
import './App.css';

function App() {
    let posts = '안녕하세요';
    let name = 'name';
    let style = {color : 'blue' , fontSize :'30px'}
    function 함수(){
      return 1000;
    }
  return (
    <div className="App">
        <div className="black-nav"></div>
        <div className={name}></div>
        <h4>{posts}</h4>
        <h4>{함수()}</h4>
        <img src={logo}/>
        <div style={ {color :'blue' , fontSize:'30px'} } >하이</div>
        <div style={ style } >하이</div>
    </div>
  );
}

export default App;
```

html 과 마찬가지로 class, style ,img , function 모두 작성이 가능하다.

