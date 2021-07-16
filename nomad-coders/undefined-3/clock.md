# clock 구현

```markup
<h2 id="clock">00:00:00</h2>
```

```javascript
const clock = document.quertSelector("h2#clock");
```

#### setInterval

setInterval\(argument\(함수\), argument\(시간\)\)

```javascript
function sayHello(){
	console.log("hello")
}
setinterval(sayHello, 500) 
// sayHello 를 0.5초에 한번씩 실행 즉 함수를 특정시간마다 실행시켜주는것
```

#### timeouts and dates

setTimeout\(argument\(함수\), argument\(시간\)\)

```javascript
function sayHello(){
	console.log("hello")
}
setTimeout(sayHello, 500)  
//sayHello 를 0.5 초 뒤에 실행 즉 함수를 특정시간 후에 실행시키는
```

#### 시간 확인하기

```javascript
new
```

