# Organizing Data with Arrays

```text
const monday ="Mon"
const tue = "Tue"
const wed = "Wed"
const thu = "Thu"
const fri = "Fri"
const sat = "Sat"
const sun = Sun"

console.log(monday,tue,wed,thu,fri,sat,sun) // 비효울적인 코드 
```

```text
const daysOfWeek = ["Mon", "Tue", "Wed", "Thu", "Fri", "Sat", "Sun"];
console.log(daysOfWeek); // [ 'Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun' ]
console.log(daysOfWeek[3]);  // Thu
console.log(daysOfWeek[400]); // undefined
```

{% hint style="info" %}
camel case : 변수는 소문자로 시작해서 띄어쓰기가 필요할때는 대문자를 이용하는 방식
{% endhint %}

