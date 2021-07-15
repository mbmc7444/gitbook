# this

함수 내에서 함수 호출 맥락\(context\)를 의미, 즉 함수를 어떻게 호출하느냐에 따라서 this가 **가리키는 대상이 달라진다**는 뜻이다.

```javascript
function func(){
    if(window === this){
        document.write("window === this");
    }
}
func();  
```

```javascript
var o = {
    func : function(){
        if(o === this){
            document.write("o === this");
        }
    }
}
o.func();  //o 안에있는 func가 실행된다
```

#### 생성자의 호

```javascript
var funcThis = null; 
 
function Func(){
    funcThis = this; // var 이 없기때문에 전연변수를 가리킨다.
}
var o1 = Func();
if(funcThis === window){ 
// 함수를 호출하면 window의 메소드이기때문에 window 가리킴
    document.write('window <br />');
}
 
var o2 = new Func();
if(funcThis === o2){
// 생성자 이기때문에 객체가 된다 즉 funcThis의 this 는 o2가된
    document.write('o2 <br />');
}
```

```javascript
function Func(){
    document.write(o);
}
var o = new Func(); // undefined
/*
생성자가 실행되기전에는 객체는 변수에 할당되지 않기때문에 o는 undefined가 나온
```

### apply, call

```javascript
var o = {}
var p = {}
function func(){
    switch(this){
        case o:
            document.write('o<br />');
            break;
        case p:
            document.write('p<br />');
            break;
        case window:
            document.write('window<br />');
            break;          
    }
}
func(); //window  함수 안에 this window이기때문에
func.apply(o); //o
func.apply(p);//p
```

ex\)

```javascript
let person1 = {
    name: 'Jo'
};

let person2 = {
    name: 'Kim',
    study: function() {
        console.log(this.name + '이/가 공부를 하고 있습니다.');
    }
};

person2.study(); // Kim이/가 공부를 하고 있습니다.

// call()
person2.study.call(person1); // Jo이/가 공부를 하고 있습니다.

```

{% hint style="info" %}
call apply 의  차이는 apply의 경우 매개변수를 배열 형태로 넣어준다는것이다.
{% endhint %}

#### 

