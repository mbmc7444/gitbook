# 클로저

내부함수가 외부함수의 맥락에 접근할수있는

```javascript
function outter(){ // 외부함수
    function inner(){ // 내부함
        var title = 'coding everybody'; 
        alert(title); 
    }
    inner();
}
outter(); //coding everybody 즉 외부함수를 실행하면 내부함수가 실행된다
```

```javascript
function outter(){
    var title = 'coding everybody';  
    function inner(){        
        alert(title);
    }
    inner();
}
outter();
//내부함수는 외부함수의 지역변수에 접근할 수 있다. 익명함수의 개념과 비슷하다고 볼수있다.
```

내부함수는 외부함수의 지역변수에 접근 할 수 있는데 외부함수의 실행이 끝나서 외부함수가 소멸된 이후에도 내부함수가 외부함수의 변수에 접근 할 수 있다. 

```javascript
function outter(){
    var title = 'coding everybody';  
    return function(){        
        alert(title);
    }
}
inner = outter();
inner(); // coding everybody
```

