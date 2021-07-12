# Javascript란 무엇인가?

Javascript 는 웹에 쓰이는 하나뿐인 프로그래밍 언어이다.

javascript로 만들수 있는 것들

* TO DO LIST 를 작성하는 웹브라우저
* 날씨를 확인할 수있는 웹 브라우저
* 앱
* game
* 실시간 채팅 등

#### 바닐라 자바스크립트\(Vanilla JS\)

바닐라 자바스크립트는 Library 가 없는 순수한  자바스크립트이다.

바닐라 자바스크립트를 능숙하게 하는 사람들은 많지않다. 어렵거나 불편하다는 이유로 Library, Framework 같은것들만 배우려고한다. 기본을 충실하게 해놓고 다음단계로 넘어간다면 좀더 쉽게 이해 할수 있을것이다.

```markup
<script src=“index.js”></script>  //스크립트를 불러오는 방법
```

#### 스크립트의 위치가 body 태그 안의 최하단에 위치해야 하는 이유

HTML을 읽는 과정에서 중간에 스크립트를 만나면 스크립트 로드와 실행을 위해서 중단되는 시점이 생기고, 그에 따라 그 만큼 브라우저 로딩 시간이 길어진다.

HTML 파싱이 끝나고 DOM 트리가 생기기 전 자바스크립트가 실행되어 DOM 조작을 할 경우 에러가 발생할 수 있다.
