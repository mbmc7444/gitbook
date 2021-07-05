# 리펙토링\(refactoring\)

#### 비효율적인 코드를 효율적으로 바꾼다-&gt; 가독성을 높이고 유지보수를 편하게한다\(반복되는 코드를 줄인다\)

이벤트 안에서 실행되는 코드는 해당 코드가 속해있는 태그를 가리키도록 태그를 직접 넣는것이아닌 this를 활용한다.

```text
  <input id="night_day" type="button" value="night" onclick="
    var target = document.querySelector('body');
    if(this.value === 'night'){
      target.style.backgroundColor = 'black';
      target.style.color = 'white';
      this.value = 'day';
    } else {
      target.style.backgroundColor = 'white';
      target.style.color = 'black';
      this.value = 'night';
    }
  ">
```

