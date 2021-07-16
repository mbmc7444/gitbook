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
setInterval(sayHello, 500) 
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
new Date();
// Sat Jul 17 2021 02:36:26 GMT+0900 (대한민국 표준시)
```

* getDate\(\) 
* getDay\(\) 
* getFullYear\(\)
* geyHours\(\)
* getMinutes\(\)
* getSeconds\(\)

```javascript
function getClock(){

const date = new Date();
const hours = String(data.getHours()).padStart(2,"0");
const minutes = String(data.getMinutes()).padStart(2,"0");
const seconds = String(data.getSeconds()).padStart(2,"0");
clock.innerText =`${hours}:${minutes}:${seconds}`;

}

getClock();
setInterval(getClock, 1000)
 // website 가 load되자마자 getClock 를 한번실행하고 매초마다 실행

```

string 앞에 string 추가하기

* padStart\(\)
* padEnd\(\)

```javascript
padStart(2, "0") // 만약 string 이 2글자가 아니라면 앞에 0을붙여줘
즉 (글자수 넣을값)
padEnd(2, "0") //만약 string 이 2글자가 아니라면 뒤에 0을붙여줘
/*
Number는 사용할수없기 때문에 Sting()을 해줘야한다.

00:00:0 -> 00:00:00 으로 바꾸는과정이다.

*/
```

