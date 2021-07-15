# 표준 내장 객체의 확장

표준 내장 객체\(Standard Built-in Object\)는 자바스크립트가 기본적으로 가지고 있는 객체들을 의미

* Object 객
* Function 함
* Array 배
* String 문
* Boolean
* Number 숫
* Math
* Date 날
* RegExp 정규표현

```javascript
var arr = new Array('seoul','new york','ladarkh','pusan', 'Tsukuba');
function getRandomValueFromArray(arr){
    var index = Math.floor(arr.length*Math.random());
    return arr[index]; 
}
console.log(getRandomValueFromArray(arr));
```

```javascript
Array.prototype.random = function(){
    var index = Math.floor(this.length*Math.random());
    return this[index];
}
var arr = new Array('seoul','new york','ladarkh','pusan', 'Tsukuba');
console.log(arr.random());
```

