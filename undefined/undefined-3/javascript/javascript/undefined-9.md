# 모듈

* 유지보수에 좋다.
* 재활용성이높아진다.
* 필요한 코드만 로드하기때문에 메모리 낭비를 줄일수있다.

```javascript
        function welcome(){
            return 'Hello world'
        }
        alert(welcome());
```

#### 모듈화 작업

```javascript
// 모듈할 파일을 만든다. greeting.js
function welcome(){
    return 'Hello world';
}
```

```markup
<html>
<head>
    <meta charset="utf-8"/>
    <script src="greeting.js"></script>
</head>
<body>
    <script>
        alert(welcome());
        console.log(welcome());
        console.log(welcome());
        console.log(welcome());
        console.log(welcome());
    </script>
</body>
</html>
```

### Node.js에서의 모듈의 로드

{% tabs %}
{% tab title="node.circle.js \(로드될 대상\)" %}
```javascript
var PI = Math.PI;
  
exports.area = function (r) {
return PI * r * r;
};
  
exports.circumference = function (r) {
return 2 * PI * r;
};
```
{% endtab %}

{% tab title="node.demo.js \(로드의 주체\)" %}
```javascript
var circle = require('./node.circle.js');
console.log( 'The area of a circle of radius 4 is '+ circle.area(4));
```
{% endtab %}
{% endtabs %}

### 라이브러리

자주 사용되는 로직을 재사용하기 편리하도록 잘 정리한 일련의 코드들의 집합

```markup
<!DOCTYPE html>
<html>
<head>
    <script src="https://code.jquery.com/jquery-1.11.0.min.js"></script>
</head>
<body>
    <ul id="list">
        <li>empty</li>
        <li>empty</li>
        <li>empty</li>
        <li>empty</li>
    </ul>
    <input id="execute_btn" type="button" value="execute" />
    <script type="text/javascript">
     $('#execute_btn').click(function(){
        $('#list li').text('coding everybody');
     })
    </script>
</body>
</html>
```

