# 숫자와 문자

### 숫자\(Number\)

Javascript에서 사용되는 data type중 하나로 Javascript 에서는 큰따옴표\("\)나 작은따옴표\('\)가 붙지 않은 숫자는 숫자로 인식한다.

```text
aleart(1); // 1
aleart(1+1); // 2 
aleart(1 * 5) // 5
aleart(4/2) // 2
```

#### Math : Javascript 사용되는 연산 매소드중하나이다.

```text
Math.pow(3,2);       // 9,   3의 2승  제곱
Math.round(10.6);    // 11,  10.6을 반올림 
Math.ceil(10.2);     // 11,  10.2를 올림
Math.floor(10.6);    // 10,  10.6을 내림
Math.sqrt(9);        // 3,   3의 제곱근
Math.random();       // 0부터 1.0 사이의 랜덤한 숫자 
```

{% hint style="info" %}
Math.random\(\)  1보다 작은 소수점이 랜덤으로 나온다

만약 반올리고싶다면. Math.round\(Math.random\(\)\) 하면된다
{% endhint %}

### 문자\(String\)

Javascript에서 사용되는 data type중 하나로 숫자와는 다르게 큰따움표나 작은따움표중 하나로 감싸야한다.

```text
aleart("hello world") o
aleart('hello world') o
aleart("hello world') x
aleart("hello world'") o
```

```text
aleart("1")  숫자를 큰따움표나 작은따움표중 하나로 깜싸게되면 문자가된다
```

문자안에 작은따움표나 큰따움표를 넣고싶을때

```text
alert('egoing's javascript') x
alert('egoing\'s javascript') o
```

줄바꿈을 하고싶다면 \n 추가하면된다

```text
alert("안녕하세요.\n생활코딩의 세계에 오신 것을 환영합니다"); 
```

문자로 더하기를 할경우

```text
aleart("coding"+" everybody"); 
```

숫자에 큰따움표를 넣게되면 문자가된다.

```text
aleart("1"+"1")
```

length : 문자의 길이를 확인할때 사용된다.

IndexOf: 문자의 자리를 확인할수있다.

```text
qwe.indexof("q") // 0
qwe.indexof("w") // 1
```

[https://opentutorials.org/course/50/37](https://opentutorials.org/course/50/37)  확인하기

