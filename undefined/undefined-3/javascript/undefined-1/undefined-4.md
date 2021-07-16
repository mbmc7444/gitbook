# 데이터 타입

객체 데이터 타입은 참고 데이터 타입이다.

원 데이터 타입은 기본 데이터 타입이다.

* 숫자
* 문자열
* 불리언\(true/false\)
* null
* undefined

객체가 아닌 데이터 타입을 원시 데이터 타입\(primitive type\)이라고 한다. 그 외의 모든 데이터 타입들은 객체다.

#### 레퍼 객체

```javascript
var str = 'coding';
console.log(str.length);        // 6
console.log(str.charAt(0));     // "C"
```

{% hint style="info" %}
. Obact access operator  객체 접근 연산자 라고한다.
{% endhint %}

```javascript
var str = 'coding';
str.prop = 'everybody'; 
// 문자열을 객체처럼 사용하면 자바스크립트가 내부적으로  객체화함
console.log(str.prop);      // undefined
//그러나 다음코드 행으로 넘어가면 다시 string으로 돌아가기때문이다,
```

