# 반복문

#### 순서대로 실행되는 프로그램의 실행순서의 흐름을 제어하는 문이다라고 할수있다.

```text
<script>
    document.write('<li>1</li>');
    var i = 0;
    while(i < 3){
      document.write('<li>2</li>');
      document.write('<li>3</li>');
      i = i + 1;
    }
    document.write('<li>4</li>');
</script>
```

{% hint style="info" %}
무한이 반복되기때문에 언제 종료될지를 정확하게 입력해야한다.

 그렇기에 관습적으로 변수 i를 만들고 그 안에 반복횟수를 정해놓는다
{% endhint %}

