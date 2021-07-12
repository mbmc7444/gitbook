# event

#### 웹브라우저 안에 일어나는 어떤 사건을 이벤트라한다

```text
<input type="button" value="hi" onclick="alert('hi')">
<input type="text" onchange="alert('changed')">
<input type="text" onkeydown="alert('key down!')">
```

{% tabs %}
{% tab title="onclick" %}
어떤 태그를 클릭했을때, 이벤트가 발생하게된다

```text
<input type="button" value="hi" onclick="alert('hi')">
```
{% endtab %}

{% tab title="onchange" %}
어떤 태그안에 요소의 값이 바뀌게 되면 이벤트가 발생된다

```text
<input type="text" onchange="alert('changed')">
```
{% endtab %}

{% tab title="onkeydown" %}
어떤 태그안에 키보드를 입력했을때, 이벤트가 발생된

```text
<input type="text" onkeydown="alert('key down!')">
```
{% endtab %}
{% endtabs %}



#### [https://www.w3schools.com/jsref/dom\_obj\_event.asp](https://www.w3schools.com/jsref/dom_obj_event.asp)

