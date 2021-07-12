# 배열과 반복문

데이타가 바뀜에따라 코드를 바꾸는거는 비합리적이기때문에 데이타가 바뀌면 그바뀐 데이타에 따라 원하는 값이 출력되게하는게 가장좋다.

```text
    <script>
      var array = ["name", "age", "gender"]
    </script>
    <h2>array</h2>
    <ul>
      <script>
        var i = 0;
        while(i < array.length){
          document.write('<li><a href="http://a.com/'+array[i]+'">'+array[i]+'</a></li>');
          i = i + 1;
        }
      </script>
```

{% hint style="info" %}
array.length

배열값에 갯수를 확인할수 있고, 그렇게 되면 i의 반복횟수를 정할수 있다
{% endhint %}

