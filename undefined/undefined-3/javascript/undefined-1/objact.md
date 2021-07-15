# Objact

Object 객체는 객체의 가장 기본적인 형태를 가지고 있는 객체이다.

```javascript
var grades = {'egoing': 10, 'k8805': 6, 'sorialgi': 80};
```

자바스크립트의 모든 객체는 Object 객체를 상속 받는데, 그런 이유로 모든 객체는 Object 객체의 프로퍼티를 가지고 있다.

{% hint style="info" %}
\(object\) -&gt; ultra -&gt; super -&gt;sub 
{% endhint %}

```javascript
Object.prototype.contain = function(neddle) {
    for(var name in this){
        if(this[name] === neddle){
        // 이 객체의 name 값들 
        // o = egoing , seul  a= 'egoing','leezche','grapittie'
            return true;
        }
    }
    return false;
}
var o = {'name':'egoing', 'city':'seoul'}
console.log(o.contain('egoing')); //this o 
var a = ['egoing','leezche','grapittie'];
console.log(a.contain('leezche')); // this a
```

Object 객체는 확장하지 않는 것이 바람직하다. 왜냐하면 모든 객체에 영향을 주기 때문이다.

```javascript
for(var name in o){
    console.log(name);  
    // 기존에 정의한 o의 값들만 나오는것이아니라 contain가 포함되서 나오게된
}
```

```javascript
for(var name in o){
    if(o.hasOwnProperty(name)) //true false
        console.log(name);  
}
/*
프로퍼티의 해당 객체의 소속인지를 체크할수있다. 즉 o안에 해당객체들의 name만을 가저온다
contain 은 부모한테 상속되어 내려온 것이기때문에 직접적인 소유가 아니다
*/
```

