# Functions part One

#### 반복해서 사용해야할 코드 조각 

#### function\(함\) 생성

```javascript
function sayHello(){
	console.log(“Hello my name is”)
};
```

#### function\(함\)실행

```javascript
sayHello();
```

#### Argumnet\(인자\)

 함수를 실행하는동안 어떤 정보를 함수에 보내고 싶을때 사용

```javascript
function sayHello(nameOfPerson, age){
	document.write("Hello my name is "+nameOfPerson+" and I’m " +age+ "!")
};

sayHello(“nico”, 10);  // Hello my name is nico and I'm 10!
sayHello(“dal”, 23);// Hello my name is dal and I'm 23!
sayHello(“lynn”, 21); // Hello my name is lynn and I'm 21!


```

```javascript
function plus(a, b){ 	console.log(a + b)
};

plus() // NaN = Not a Number 숫자가 아니다
```

{% hint style="info" %}
계산식에 값을 넣지않을때  NaN 이뜬다.  

String 이면 underlined
{% endhint %}

```javascript
function plus(firstNumber , secondNumber){
	console.log(firstNumber + secondNumber)
}


function divide(a, b){ 	console.log(a / b)
}


plus(60 ,8) // 68
divide(98, 20) // 4.9
```

{% hint style="info" %}
console.log\(firstNumber\) , console.log\(b\) 

인자는 함수안에서 존재하는 값이므로 함수 밖에서 불러올경우 오류가 생긴다
{% endhint %}

#### 객체 안의 함수

```javascript
const player  = {	
  name : "nico",
	sayHello : function(otherPersonsName){		   
    document.write("hello " + otherPersonsName+ " nice to meet you!");
	},
};


player.sayHello("lynn"); // hello lynn nice to meet you!
```

#### return

function 값을 출력하고싶을 때 사용. 

```javascript
Const age = 96;
function calculateKrAge(ageOfForeigner){
	return ageOfForeigner + 2;

}; 
Const krAge = calculateKrAge(age);;
```

```javascript
const calculator = {
    plus: function(a, b){
    return a + b
  },
    minus: function(a, b){
    return a - b
  },
    times: function(a, b){
    return a * b
  },
    divide: function(a, b){
    return a / b
  },
    power: function(a, b){
    return a ** b
  }
};



const plusResult = calculator.plus(2,3); //5
const minusResult = calculator.minus(plusResult , 10);//-5
const timesResult = calculator.times(10 , minusResult); // -50
const divideResult = calculator.divide(timesResult, plusResult); //-10
const powerResult = calculator.power(divideResult , minusResult); // -0.000009999999999999999
```

{% hint style="info" %}
함수에서 return 을 만나면 값을 출력하고 함수를 종료한다.
{% endhint %}



