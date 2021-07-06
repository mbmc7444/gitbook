# 반복문

### 반복문\(loop\)

#### while

```text
while (조건){
    반복해서 실행할 코드
}
```

```text
while(true){
    document.write('coding everybody <br />');
}. //
```

{% hint style="info" %}
반복문 코드를 작성할때, 주의사항은 위에 코드는 반복의 횟수를 정하지 않기때문에 무한하게 반복한다 그렇기에 항상 주의하면서 코드를 작성하자

document.write는 자바스크립트를 이용해서 웹페이지에 텍스트를 출력한다.
{% endhint %}

```text
var i = 0;
while(i < 10){ 
    document.write('coding everybody <br />');
    // i의 값이 1씩 증가한다.
    i++
}

```

#### for

* 초기화 구문
* 반복조건
* 반복이 될때마다 실행되는 구문

while 은 3가지의 코드가 분리되서 작성된다 그렇기에 코드가 복잡해 질경우 오류가 생길수 있으며, 가독성 또한 문제가 된다 이걸 해결할수 있는것이 for이다 \(for가 정답은아니다\)

```text
for(초기화; 반복조건; 반복이 될 때마다 실행되는 코드){
    반복해서 실행될 코드
}
```

```text
for(var i = 0; i < 10; i++){
    document.write('coding everybody'+i+'<br />');
}
```

{% hint style="info" %}
I= I+1 , i++ 유사하다. for문에 모두 사용가능하다

I++ 자기 자신을 먼저 실행하고 반복한다 ++I 증가를 시키고 반복한다.
{% endhint %}

#### 반복문 제어

#### break : 반복작업을 중간에 중단할때 사용

```text

for(var i = 0; i < 10; i++){
    if(i === 5) {
        break;
    }
    document.write('coding everybody'+i+'<br />');
}

/*
coding everybody 0
coding everybody 1
coding everybody 2
coding everybody 3
coding everybody 4
*/

```

#### continue : 반복작업을 그순간에 중단 했다가 다시 작업을 시작할때 사용

```text
for(var i = 0; i < 10; i++){
    if(i === 5) {
        continue;
    }
    document.write('coding everybody'+i+'<br />');
}


/*
coding everybody 0
coding everybody 1
coding everybody 2
coding everybody 3
coding everybody 4
coding everybody 6
coding everybody 7
coding everybody 8
coding everybody 9
*/
```

#### 반복문 중첩

반복문안에 새로운 반복문을 넣을수 있다.

```text
// 0부터 9까지 변수 i에 순차적으로 값을 할당        
for(var i = 0; i < 10; i++){
    // 0부터 9까지의 변수를 j의 값에 순차적으로 할당
    for(var j = 0; j < 10; j++){    
        // i와 j의 값을 더한 후에 출력
        // String은 숫자인 i와 j의 데이터 타입을 문자로 형태를 변환하는 명령이다. 
        // String()을 제거하고 실행해보면 의미가 좀 더 분명하게 드러날 것이다.
        document.write(String(i)+String(j)+'<br />');
    }
}

/*
시간의 순서대로 순차적으로 코드가 실행되므로
 먼저 i 가 한번 실행되고 안에 반복문이 실행된다.
 즉 0 다음에 j 0 ~ 9 이 출력되고 난후
 다시 i 의다음 반복인 1이 출력되고 난후 
 다시한번 j 0 ~9 이 출력된다 
 이렇게 i 10번 실행되고 j 100번 실행된다
```

{% hint style="info" %}
debug_\(_debugging_\) :_ 오류를 해결행위

_debugger : 오류를 해결하는 행위를 하기위한 도구_

코드가 어떤방식으로 실행되고 출력되는지 확인 하는 유용한 과정이다.
{% endhint %}

