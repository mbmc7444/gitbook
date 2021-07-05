# 함수의 활용

함수는 리펙토링에 있어 가장 중요한 요소이다.

복잡해진 코드를 여러군대에서 사용할경우 반복적으로 작성한다면 문제가 발생할수있다.

그러므로 js를 따로 만들어 보관하여 사용한다면 좀더 간결한 코드를 완성시킬수있다.

{% tabs %}
{% tab title="html" %}
```text
  <input id="night_day" type="button" value="night" onclick="
    nightDayHandler(this);
  ">
  <input id="night_day" type="button" value="night" onclick="
    nightDayHandler(this);
  ">
```
{% endtab %}

{% tab title="js" %}
```text

function nightDayHandler(self){
    var target = document.querySelector('body');
    if(self.value === 'night'){
      target.style.backgroundColor = 'black';
      target.style.color = 'white';
      self.value = 'day';
      var alist = document.querySelectorAll('a');
      var i = 0;
      while(i < alist.length){
        alist[i].style.color = 'powderblue';
        i = i + 1;
      }
    } else {
      target.style.backgroundColor = 'white';
      target.style.color = 'black';
      self.value = 'night';
      var alist = document.querySelectorAll('a');
      var i = 0;
      while(i < alist.length){
        alist[i].style.color = 'blue';
        i = i + 1;
      }
    }
  }
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
이때 처음 코드에 this를 사용하지 않는 이유는 js로 따로 함수를 만들경우 , 전역개체로 인식하여 해당 태그가 아닌 window를 가리키게된다. 그러므로 매개변수와 인자를 활용하여 해결하여야한다.
{% endhint %}

