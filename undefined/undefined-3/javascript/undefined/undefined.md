# 유효범위

#### 전역변수 와 지역변수

* 전역변수는 함수 외부에서 선언된 변수로, 프로그램 전체에서 접근할 수 있는 변수입니다.
* 지역변수는 함수 내부에서 선언된 변수로, 함수가 실행되면 만들어지고 함수가 종료되면 소멸하는 변수입니다. 함수 외부에서는 접근할 수 없습니다.

```javascript
var vscope = 'global'; //함수 밖에서 변수를 선
function fscope(){
    alert(vscope);
}
fscope(); 
```

```javascript
var vscope = 'global';
function fscope(){
    var vscope = 'local';
    alert('함수안 '+vscope); // 함수가 실행되고 변수 vscope =local
}
fscope();
alert('함수밖 '+vscope); // 함수가 종료되고 변수 vscope = global
```

#### 전역변수를 사용해야 할경우 

```javascript
MYAPP = {}
MYAPP.calculator = {
    'left' : null,
    'right' : null
}
MYAPP.coordinate = {
    'left' : null,
    'right' : null
}
// 객체안에 넣어 사용하게되면 그나마 충돌을 최소화할수있다.
(function(){
    var MYAPP = {}
    MYAPP.calculator = {
        'left' : null,
        'right' : null
    }
    MYAPP.coordinate = {
        'left' : null,
        'right' : null
    }
}())
// 그게 아니라면  익명함수로 실행하자
```

```javascript
var i = 5;
 
function a(){
    var i = 10;
    document.write(i); // i = 10
    b();
}
 
function b(){
    document.write(i);
}

a() // i = 5 가 된다
```

