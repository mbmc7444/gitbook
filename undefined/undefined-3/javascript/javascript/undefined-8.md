# 객체

### 객체\(Objact\)

#### 객체 생성

```text
var grades = {'egoing': 10, 'k8805': 6, 'sorialgi': 80};
```

```text
var grades = {};
grades['egoing'] = 10;
grades['k8805'] = 6;
grades['sorialgi'] = 80;

```

```text
var grades = new Object();
grades['egoing'] = 10;
grades['k8805'] = 6;
grades['sorialgi'] = 80;
```

#### 객체를 가져오는방법

```text
var grades = {'egoing': 10, 'k8805': 6, 'sorialgi': 80};
alert(grades['sorialgi']); // 80
```

```text
alert(grades.sorialgi);
```

{% hint style="info" %}
배열과는 다르게 객체의 index 문자이다.
{% endhint %}

```text
var grades = {'egoing': 10, 'k8805': 6, 'sorialgi': 80};
for(key in grades) {
    document.write("key : "+key+" value : "+grades[key]+"<br />");
} 
/*
key : egoing value : 10
key : k8805 value : 6
key : sorialgi value : 80
*/

//grades 객체안에 들어있는 값들의 key 가져와서 
변수 key안에 넣고 출력한

```

#### 따로 검색한 것들

ES6 문법에서 새로나온 것들인데 key value 값을 구할수있다.

* Object.keys\(grades\) : key
* Object.values\(grades\) :value
* Object.entries\(grades\) :key

```text
object.keys(grades) // ["egoing", "k8805", "sorialgi"]
object.values(grades) //[10, 6, 80]
object.entries(grades) 
/*
0: (2) ["egoing", 10]
1: (2) ["k8805", 6]
2: (2) ["sorialgi", 80]
*/
```



#### 객체 지

객체 안에 연관 데이터\(list\), 함수\(show\)를 그룹핑한 것들을 객체 지향이라 부른다.

```text
var grades = {
    'list': {'egoing': 10, 'k8805': 6, 'sorialgi': 80},
    'show' : function(){
        for(var name in this.list){
            document.write(name+':'+this.list[name]+"<br />");
        }
    }
};
grades.show(); / 객체.함수명() 함수를 실행할수있다.
```

#### 

변수 안에있는 객체는 list라는 키가 있고, 그안에 값은 또다른 객체이다.

{% hint style="info" %}
this는 함수를 갖고 있는 객체\(grades\)를 가리킨다.

console.log\(\) , 를 넣으면 여러값을 콘솔창에 출력할수 있다.
{% endhint %}

#### 

