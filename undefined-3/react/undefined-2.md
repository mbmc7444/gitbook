# 리액트 시작

1. node.js 설치
2. vscode 터미널 

```text
npx create-react-app 만들고싶은 파일명
```

{% hint style="info" %}
**boilerplate : 리액트 라이브러리**

create-react-app 
{% endhint %}

```text
npm start
```

App.js 가 메인에 들어갈 코드를 작성하는곳이며 , index.html 과 유사하다가 볼수있다.

```jsx
import logo from './logo.svg';
import React from 'react';
import './App.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;
```

