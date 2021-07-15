# 생성자와 new

```javascript
var person = {}
person.name = 'egoing'; //객체 name = egoing 을 만든다
person.introduce = function(){
    return 'My name is '+this.name; 
    // this 는 이 함수를 담고있는 객체를 말한다.
}
document.write(person.introduce());
```

{% hint style="info" %}
객체 내의 변수를 프로퍼티\(property\) 함수를 메소드\(method\) 라한다
{% endhint %}

```javascript
var person = {
    'name' : 'egoing',
    'introduce' : function(){
        return 'My name is '+this.name;
    }
}
document.write(person.introduce());
```

{% hint style="info" %}
빈 객체를 만들고 그안에 값을 넣는것보다 객체를 만들고 그안에 값을 직접 넣는것이 코드가 좀더 직관적으로 보일수있다.
{% endhint %}

#### new

빈 함수를 변수에 담아서 변수를 부르게 되면 undefined 가 나오게되지만, **new** 를 붙이게 되면 객체로써 불러올수있다.

```javascript
function Person(){}
var p = new Person();
p.name = 'egoing';
p.introduce = function(){
    return 'My name is '+this.name; 
}
document.write(p.introduce());
```

```javascript
function Person(name){
    this.name = name;
    this.introduce = function(){
        return 'My name is '+this.name; 
    }    
}
var p1 = new Person('egoing');
document.write(p1.introduce()+"<br />");
 
var p2 = new Person('leezche');
document.write(p2.introduce());

// 여러번의 함수를 작성할 필요없이 함수 하나만을 만들고, p1 ,p2 .... 객체로 생성시킬수있다.
```



