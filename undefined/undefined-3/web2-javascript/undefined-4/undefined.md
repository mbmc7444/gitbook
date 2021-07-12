# 객체

#### 객체는 복잡하게 넣어놓지 않고 정리해서 넣어둘때 사용한다.

```text
var person = {
  name: ['Bob', 'Smith'],
  age: 32,
  gender: 'male',
  interests: ['music', 'skiing'],
};
```

```text
    <script>
      var coworkers = {
        "programmer":"egoing",
        "designer":"leezche"
      };
      document.write("programmer : "+coworkers.programmer+"<br>");
      document.write("designer : "+coworkers.designer+"<br>");
      coworkers.bookkeeper = "duru"; // 객채에 데이터를넣을때,
      document.write("bookkeeper : "+coworkers.bookkeeper+"<br>");
      coworkers["data scientist"] = "taeho"; // 띄어쓰기가된 값을 객체에 데이터를넣을때
      document.write("data scientist : "+coworkers["data scientist"]+"<br>");
    </script>
```

### 객체와 반복문

```text
      for(var key in coworkers) {
            //coworkers의 key값을 가져오는 반복
      }
```

{% hint style="info" %}
배열에서의 반복문은  index를 사용하지만 객체같은경우는 "programmer","designer"같은 key값을 이용해서 구할수있다.
{% endhint %}

### 프로퍼티와 메소드

```text
   <script>
      coworkers.showAll = function(){
        for(var key in this) {
          document.write(key+' : '+this[key]+'<br>');
        }
      }
      coworkers.showAll();
    </script>
```

객체에 소속된 함수\(showAll\)를 만들수있다.

이때 소속된 함수를 매소드라 부른다.

객체에 소속된 값을 프로퍼티라고 부른다. \(ex:programmer\)



