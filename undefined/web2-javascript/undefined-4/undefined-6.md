# 배열과 반복문의 활용

```text
 <input id="night_day" type="button" value="night" onclick="
    var target = document.querySelector('body');
    if(this.value === 'night'){
      target.style.backgroundColor = 'black';
      target.style.color = 'white';
      this.value = 'day';

      var alist = document.querySelectorAll('a');
      var i = 0;
      while(i < alist.length){
        alist[i].style.color = 'powderblue';
        i = i + 1;
      }
    } else {
      target.style.backgroundColor = 'white';
      target.style.color = 'black';
      this.value = 'night';

      var alist = document.querySelectorAll('a');
      var i = 0;
      while(i < alist.length){
        alist[i].style.color = 'blue';
        i = i + 1;
      }
    }
  ">
```

기존의 버튼들은 하나하나 만들어야했고, 수백  수천개를 만들게 되면 비합리적인 코드가 되기때문에

