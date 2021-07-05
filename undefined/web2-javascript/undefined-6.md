# 라이브러리와 프래임워크

#### Framework vs Library

프레임워크는 전체적인 흐름을 스스로가 쥐고 있으며 사용자는 그 안에서 필요한 코드를 짜 넣으며 반면에 라이브러리는 사용자가 전체적인 흐름을 만들며 라이브러리를 가져다 쓰는 것이라고 할 수 있습니다.  
  
출처: [https://webclub.tistory.com/458](https://webclub.tistory.com/458) \[Web Club\]

#### Library

jquery

```text
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>
```

```text
var Links = {
  setColor:function(color){
    var alist = document.querySelectorAll('a');
    var i = 0;
    while(i < alist.length){
      alist[i].style.color = color;
      i = i + 1;
    }
    // var alist = document.querySelectorAll('a');
    // var i = 0;
    // while(i < alist.length){
    //   alist[i].style.color = color;
    //   i = i + 1;
    // }
    $('a').css('color', color);
  }
}
    var Body = {
  setColor:function (color){
    document.querySelector('body').style.color = color;
    //document.querySelector('body').style.color = color;
    $('body').css('color', color);
  },
  setBackgroundColor:function (color){
    document.querySelector('body').style.backgroundColor = color;
    // document.querySelector('body').style.backgroundColor = color;
    $('body').css('backgroundColor', color);
  }
}
```

jquery 가 javascript 보다 좀더 쉽고 직관적으로 짤수있다. 그러나 정답은 아니다.

