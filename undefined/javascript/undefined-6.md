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



