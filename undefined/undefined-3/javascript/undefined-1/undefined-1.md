# 전역객체

javascript 에서 모든 객체는 전역개체의 프로퍼티다

```javascript
function func(){
    alert('Hello?');    
}
func();
window.func(); // window 객체 .func() 속성(메소드)
```

```javascript
var o = {'func':function(){
    alert('Hello?');
}}
o.func();
window.o.func();
```

[https://opentutorials.org/course/50/44](https://opentutorials.org/course/50/44)

