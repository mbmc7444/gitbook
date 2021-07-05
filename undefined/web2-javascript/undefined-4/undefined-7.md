# 함수

#### 함수 \(function\) 란 JavaScript에서 기본적인 구성 블록 중의 하나이. 함수는 작업을 수행하거나 값을 계산하는 문장 집합 같은 자바스크립트 절차입니다

방대해진 코드로 인해 웹페이가 커지고 그렇게되면 인터넷에 전송될때 시간,비용이 점점 늘어나게된다. 이 문제를 최소화 할수있는것이 함수이다.

```text
      <script>
        function two(){
          document.write('<li>2-1</li>');
          document.write('<li>2-2</li>');
        } // 함수 사용 방법
        top()
      </script>
```



### 매개변수\(parameter\)와 인자\(argument\)

```text
    <script>
      function onePlusOne(){
        document.write(1+1+'<br>');
      }
      onePlusOne();
      function sum(left, right){
        document.write(left+right+'<br>');
      }
      sum(2,3); // 5
      sum(3,4); // 7
```

정해져있는 값을 출력하는 함수가 아니라 우리가 주어진 값에 의해 다른 값을 출력시켜주는 함수를 만들수있다.

function sum\(left ,right\) {

}  sum 함수 안에 들어있는 left right 변수를 매개변수\(parameter\)이라고 하며 , 함수를 실행할때마다

매개변수안에 값에 넣어주는 2,3 또는 3,4를 인자\(argument\) 라 한다.



### 리턴

```text
    <script>
      function sum2(left, right){
        return left+right;
      }
      document.write(sum2(2,3)+'<br>');
      document.write('<div style="color:red">'+sum2(2,3)+'</div>');
      document.write('<div style="font-size:3rem;">'+sum2(2,3)+'</div>');
    </script>
```

매개변수와 인자를 활용하여, left + right 값을 출력시켜줄수있다. 이때 필요한 것이 returen이다 .

{% hint style="info" %}
수많은 속성을 다르게 출력하고 싶을때, return을 사용하지 않으면 수많은 함수를 만들어야하는 문제가 생긴다 .
{% endhint %}

