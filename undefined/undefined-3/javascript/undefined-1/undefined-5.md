# 참조

#### 복

```javascript
var a = 1;
var b = a; // b에다가 a를 대입하다
b = 2;
console.log(a); // 1
```

단지 b = a 가되고 복제 했을뿐 a값이 바뀐것은 아니다

#### 참조

```javascript
var a = {'id':1};
var b = a;
b.id = 2;
console.log(a.id);  // 2
```

객체는 b. id\(**property**\)를 바꾸게 되면 a의 id\(**property**\)가 바뀌게 된다

#### 함

```javascript
var a = 1;
function func(b){
    b = 2;
}
func(a);// a = b  b =2  a=1
console.log(a);
```

마찬가지로 복제했을뿐 a를 바꾼게 아니다

```javascript
var a = {'id':1};
function func(b){
    b = {'id':2};
}
func(a);
console.log(a.id);  // 1

```

a 와 b는 하나의 객체\(id : 1\) 를 가리키지만 함수안에 b로 새로운 객체를 만들었기때문에

a 와 b는 무관해진다.

```javascript
var a = {'id':1};
function func(b){
    b.id = 2;
}
func(a);
console.log(a.id);  // 2
```

a 와 b의 데이터는 객체이므로 같은 참조를 하고 객체 안의 데이터를 바꾼것이므로 같은 참조를 하고있는 a의 id도 바뀐다

