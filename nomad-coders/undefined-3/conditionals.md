# Conditionals\(조건문\)

#### prompt\(\)

```javascript
const age = prompt("How old are you?")// 사용자에게 답을 할수있는 창을 띄울수있다.

/* javascript에서 prompt 를 사용하지않는 이유는 
창이 실행되고 있는 중에는 모든 javascript가 정지하기 때문이다. 
*/
console.log(typeof age) // 해당 type을 알려준다 (Number, String ...)
```

#### parseInt\(\)

String을 Number로 바꿔준다.

```javascript
parseInt("15") // 15 
parseInt("sdfnasfnsakdfb") // NaN 숫자가 아닌것을 입력하면 Not a Number가 뜬다.
```

```javascript
const age = parseInt(promt("How old are you?"))
```

#### isNaN\(\)

* 인자를 넣으면 그 인자가 숫지인지 아닌지 확인해준다.
* 반환값은 boolean 이다\(true, false\)
* 해석하면 인자값이 숫자가 아닙니까? 답: 아닙니다 숫자입니다\(false\) , 맞습니다 숫자가 아닙니다\(true\)

```javascript
console.log(isNaN(age)); // false 
```

### conditionals\(조건문\)

```javascript
if(conditionals){
    // conditionals === true
} else{
    // conditionals ===false
}
```

```javascript
if(isNaN(age)){
    console.log("Please write a number") // age가 숫자가 아니면 실
} else{
    console.log("Thank you for writing your age.")
}
```

