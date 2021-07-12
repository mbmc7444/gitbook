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

querySelector 매소드는 지정된 태그의 첫번째 하나만 가져온다.

querySelectorAll 매소드를 이용하면 지정된 태그의 모든 값을 배열형식으로 가져올수있다.



