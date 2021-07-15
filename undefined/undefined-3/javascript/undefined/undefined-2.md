# 값으로서의 함수

JavaScript에서는 함수도 객체다.	

```javascript
function a(){}
```

객체의 속성 값으로 담겨진 함수를 메소드\(method\)라고 부른다.

```javascript
a = {
    b:function(){
    }
};
```

함수는 값이기 때문에 다른 함수의 인자로 전달 될수도 있다.

```javascript
function cal(func, num){
    return func(num)
}
function increase(num){
    return num+1
}
function decrease(num){
    return num-1
}
alert(cal(increase, 1)); // increase 함수값을 리
alert(cal(decrease, 1)); // decreas 함수값을 리
```

함수는 함수의 리턴 값으로도 사용할 수 있다.

```javascript
function cal(mode){
    var funcs = {
        'plus' : function(left, right){return left + right},
        'minus' : function(left, right){return left - right}
    }
    return funcs[mode];
}
alert(cal('plus')(2,1)); // 2,1 -> 2 + 1 = 3
alert(cal('minus')(2,1));  // 2,1-> 2 - 1 =1
```

배열도 사용할수 있다

```javascript
var process = [
    function(input){ return input + 10;},
    function(input){ return input * input;},
    function(input){ return input / 2;}
];
var input = 1;
for(var i = 0; i < process.length; i++){
    input = process[i](input);
}
alert(input); 
/* 
process.length = 3  
i = 0,1,2
process[i]
0 일때  function(input){ return input + 10;},
1 일때 function(input){ return input * input;},
2ㅣ일때 function(input){ return input / 2;}
```

#### 콜

```javascript
var numbers = [20, 10, 9,8,7,6,5,4,3,2,1];
var sortfunc = function(a,b){
    console.log(a,b);
    if(a>b){
    return 1;
    } else if(a<b){
    return -1;
    } else{
    return 0;
    }
}
console.log(numbers.sort(sortNumber)); 



function sortNumber(a,b){
    // 위의 예제와 비교해서 a와 b의 순서를 바꾸면 정렬순서가 반대가 된다.
    return b-a;
}
var numbers = [20, 10, 9,8,7,6,5,4,3,2,1];
alert(numbers.sort(sortNumber)); // array, [20,10,9,8,7,6,5,4,3,2,1]
```

#### 비동기 처리

동기 : 어떤 작업을 시작할때, 순서대로 일을 처리하는 

비동기: 어떤 작업을 시작할때, 미리 작업된것이 실행되고 일을 처리하는  -&gt;ajax

```javascript
//json
{"title":"JavaScript","author":"egoing"}

//js
    $.get('./datasource.json.js', function(result){
        console.log(result);
    }, 'json');
    
    /*
    get 이후에 url을 작성해야한다(./datasource.json.js)
    그 url안에 있는 객체 정보를 result에 인자를 담아서 가져온다
```

