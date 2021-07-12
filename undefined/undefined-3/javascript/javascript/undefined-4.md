# 비교연산자

### 대입연산자\(=\)

```javascript
a = 1 ;
/*
a 는변수
= 대입연산자
1 상수
*/
```

### 동등연산자\(==\)

```javascript
alert(1==2)             //false
alert(1==1)             //true
alert("one"=="two")     //false 
alert("one"=="one")     //true
```

#### 일치연산자\(===\)

```javascript
alert(1=='1');              //true
alert(1==='1');             //false
```

동등연산자와는 다르게 데이터 타입이 달라질경우 같은 1이라도 false를 출력한다.

[https://dorey.github.io/JavaScript-Equality-Table/](https://dorey.github.io/JavaScript-Equality-Table/) 를 확인하면 좀더 정확한 차이를 알수있다.

{% hint style="info" %}
코드를 작성할때 특별한 상황이 아니라면 일치연산자\(===\)를 사용하자
{% endhint %}

#### 심화

```javascript
alert(null == undefined);       //true
alert(null === undefined);      //false
alert(true == 1);               //true
alert(true === 1);              //false
alert(true == '1');             //true
alert(true === '1');            //false
 
alert(0 === -0);                //true
alert(NaN === NaN);             //false
```

* null 값이 없다 프로그래머가 의도적으로 없는 값을 만들때
*  undefined 정의되지않는다 프로그래머가 의도적이지 않을때
* NaN 는 계산할수없음 이라 비교할수없다 즉 0을 0으로나눌때 같은 상황

### 부정\(!\)

! 부정을 의미한다\(같다의 부정은  !=\)

```text
alert(1!=2);            //true
alert(1!=1);            //false
alert("one"!="two");    //true
alert("one"!="one");    //false
```

### 정확한 부정\(!==\)

> ### 좌항이 우항보다 크거나 같다\(&gt;=\)

```text
alert(10>=20);      //false
alert(10>=1);       //true
alert(10>=10);      //true
```

