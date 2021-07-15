# argument

```javascript
function sum(){
    var i, _sum = 0;    
    for(i = 0; i < arguments.length; i++){
        document.write(i+' : '+arguments[i]+'<br />');
        _sum += arguments[i];
    }   
    return _sum;
}
document.write('result : ' + sum(1,2,3,4));

/*
0 : 1
1 : 2
2 : 3
3 : 4
result : 10
sum은 매개변수(parameter)가 없다.
따로 인자를 매개변수로 보내도 에러가 생기지않는다.
arguments.length = 4; 1,2,3,4 4개를 보냈기때문에
*/
```

{% hint style="info" %}
a+=1  ==   a= a+1 
{% endhint %}

```javascript
function zero(){
    console.log(
        'zero.length', zero.length,
        'arguments', arguments.length
    );
}
function one(arg1){
    console.log(
        'one.length', one.length,
        'arguments', arguments.length
    );
}
function two(arg1, arg2){
    console.log(
        'two.length', two.length,
        'arguments', arguments.length
    );
}
zero(); // zero.length 0 arguments 0 
one('val1', 'val2');  // one.length 1 arguments 2  
two('val1');  // two.length 2 arguments 1


/*
함수명.length = 함수가 매개변수로 지정된 갯수
arguments = 함수로 전달된 인자의 갯수


```

