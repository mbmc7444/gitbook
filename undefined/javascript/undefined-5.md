# 조건문

조건문이란 프로그램 내에서 주어진 표현식의 결과에 따라 별도의 명령을 수행하도록 제어하는 실행문입니다.

### if

if 문은 표현식의 결과가 참\(true\)이면 주어진 실행문을 실행하며, 거짓\(false\)이면 아무것도 실행하지 않습니다.

```text

if(true){
    alert('result : true');
}


if(false){
    alert('result : true');
}

if(false){
    alert(1);
    alert(2);
    alert(3);
    alert(4);
}
alert(5); // 5만 실행된다

```

### else

if 문과 같이 사용할 수 있는 else 문은 if 문의 표현식 결과가 거짓\(false\)일 때 주어진 실행문을 실행합니다.

```text
if(true){
    alert(1);
} else {
    alert(2);
}
```

### else if

else if 문은 if 문처럼 표현식을 설정할 수 있으므로, 중첩된 if 문을 좀 더 간결하게 표현할 수 있습니다.

하나의 조건문 안에서 if 문과 else 문은 단 한 번만 사용될 수 있습니다.

```text
if(false){
    alert(1);
} else if(true){
    alert(2);
} else if(true){
    alert(3);
} else {
    alert(4);
} //2만 실행된다
```

### 변수와 비교연산자

If 안에 가변적인 변수를 넣을수있다.

prompt : 사용자가 텍스트를 입력할 수 있도록 안내하는 선택적 메세지를 갖고 있는 대화 상자를 띄운다.

```text
prompt('당신의 나이는?');
alert(prompt('당신의 나이는?'));
```

### 예제 1

```text
    <script>
        id = prompt('아이디를 입력해주세요.');
        if(id=='egoing'){
            password = prompt('비밀번호를 입력해주세요.');
            if(password==='111111'){
                alert('인증 했습니다.');
            } else {
                alert('인증에 실패 했습니다.');
            }
        } else {
            alert('인증에 실패 했습니다.');
        }
    </script>
```

### 논리연산자

#### $$\(and\) 

&&는 좌항과 우항이 모두 참\(true\)일 때 참이된다.

```text
    <script>
        id = prompt('아이디를 입력해주세요.');
        password = prompt('비밀번호를 입력해주세요.');
        if(id=='egoing' && password=='111111'){
            alert('인증 했습니다.');
        } else {
            alert('인증에 실패 했습니다.');
        }
    </script>
```

#### \|\|\(or\)

좌우항 중에 하나라도 true라면 참이된다.

```text
id = prompt('아이디를 입력해주세요.');
if(id==='egoing' || id==='k8805' || id==='sorialgi'){
    alert('인증 했습니다.');
} else {
    alert('인증에 실패 했습니다.');
}
```

### ! \(not\)

'!'는 부정의 의미로, Boolean의 값을 역전시킨다. true를 false로 false를 true로 만든다.

```text
if(!true && !true){
    alert(1);
}
if(!false && !true){
    alert(2);
}
if(!true && !false){
    alert(3);
}
if(!false && !false){
    alert(4);
}
```

## Boolean 대체

#### 기타 false로 간주되는 데이터 형

```text

if(!''){
    alert('빈 문자열')
}
if(!undefined){
    alert('undefined');
}
var a;
if(!a){
    alert('값이 할당되지 않은 변수'); 
}
if(!null){
    alert('null');
}
if(!NaN){
    alert('NaN');
}

```

[https://dorey.github.io/JavaScript-Equality-Table/](https://dorey.github.io/JavaScript-Equality-Table/) 자세한 내용을 확인하자

