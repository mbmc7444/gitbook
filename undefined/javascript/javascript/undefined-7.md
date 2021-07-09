# 함수

### 함수\(function\)

하나의 로직을 재실행 할 수 있도록 하는 것으로 코드의 재사용성을 높여준다.

* 재사용성 : 함수를 정의하고 여러곳에서 호출 
* 편의성 : 함수를 정의하고 필요한 곳에 호출하여 사용할때 오류가 생긴다면 해당 정의된함수만 수정하면 된다.
* 생산성 : 복잡하고 방대한 코드를 작성했더라도, 다른 프로그래머들은  호출 방법만 알면 함수를 사용할수있다. 

```text
function 함수명( [인자...[,인자]] ){
   코드
   return 반환값
}

```

#### 함수의 이

*  ****괄호 안에서 쉼표로 분리된 함수의 매개변수 목록 
* 중괄호 { } 안에서 함수를 정의하는 자바스크립트 표현

```text
function numbering(){
    i = 0;
    while(i < 10){
        document.write(i);
        i += 1;
    }   
}
numbering(); // 0,1,2,3,4,5,6,7,9


```

```text
for(var i = 0; i< 10; i++){
	numbering();
} // numbering() 함수를 10번실행하는 방
```

#### 입력과 출력

retrun

1. 해당 함수 종료
2. Return 뒤에있는 값을 그함수의 출력값으로 반환

```text
function get_member1(){
    return 'egoing';
}
 
function get_member2(){
    return 'k8805';
}
 
alert(get_member1()); // egoing
alert(get_member2()); // k8805

```

```text
function get_member(){
    return 'egoing';
    return 'k8805';
    return 'sorialgi';
}
alert(get_member()); // egoing 

/*
여러 return값이 있더라도 
처음의 return값만 실행되고 함수가 종료된다
*/

```

#### 인자\(argument\)

함수로 유입되는 입력 값을 의미하는데, 어떤 값을 인자로 전달하느냐에 따라서 함수가 반환하는 값이나 메소드의 동작방법을 다르게 할 수 있다

```text
function get_argument(arg){
    return arg;
}
alert(get_argument(1)); // 1
alert(get_argument(2)); // 2
```

{% hint style="info" %}
Arg = 매개변수 \(parameter\) 숫자 1, 2 인자 라고한다
{% endhint %}

#### 복수인자

```text
function get_arguments(arg1, arg2){
    return arg1 + arg2
}
alert(get_arguments(10, 20));  
// arg1 => 10 arg2 =>20.  10+ 20 을 리턴하기때문에 30
alert(get_arguments(20, 30));  
// arg1 => 20 arg2 =>30. 20+ 30 을 리턴하기때문에 50
```

#### 함수를 정의하는 다른방법

```text
var numbering = function (){
    i = 0;
    while(i < 10){
        document.write(i);
        i += 1;
    }   
}
numbering();
```

```text
(function (){
    i = 0;
    while(i < 10){
        document.write(i);
        i += 1;
    }   
}(); 
/*
 익명함수 정의와 호출을 동시에 한다
  (이름이 필요없고 바로 실행하고싶을때 사용)
 */
```

