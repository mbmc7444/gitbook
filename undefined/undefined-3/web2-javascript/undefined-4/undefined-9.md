# 객체의 활용

여러개의 함수를 반복적으로 사용하지않고 그 함수를 객체에 넣어 코드를 짤수있다.

{% tabs %}
{% tab title="비효율적인 코드" %}
```text
function LinksSetColor(color){
        var alist = document.querySelectorAll('a');
        var i = 0;
        while(i < alist.length){
            alist[i].style.color = color;
            i = i + 1;
        }
}

function BodySetColor(color){
    document.queryselector('body').style.color = color;
}
function BodyBackgroundColor(color){
    document.queryselector('body').style.backgroundcolor = color;
}
```
{% endtab %}

{% tab title="객체로 바꾼 코드" %}
```text
var Links = {
    setColor:function(color){
        var alist = document.querySelectorAll('a');
        var i = 0;
        while(i < alist.length){
            alist[i].style.color = color;
            i = i + 1;
        }
    }
}


var Body = {
    setColor:function(color){
        document.querySelector('body').style.color = color;
    },
    setBackgroundColor:function(color){
        document.querySelector('body').style.backgroundColor = color;
    }
}

```
{% endtab %}
{% endtabs %}

```text
function nightDayHandler(self){
    var target = document.querySelector('body');
    if(self.value === 'night'){
        Body.setBackgroundColor('black');
        Body.setColor('white');
        self.value = 'day';
        Links.setColor('powderblue');
    } else {
        Body.setBackgroundColor('white');
        Body.setColor('black');
        self.value = 'night';
        Links.setColor('blue');
    }
}
```

