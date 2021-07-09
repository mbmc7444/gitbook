# slice\(\)

문자열의 일부를 추출하면서 새로운 문자열을 반환

```text
arr.slice([begin[, end]])
```

```text
const arr = [1,2,3,4,5];

let sliceArr = arr.slice(2,5) //index 2 ~ 4

document.write(arr) // 1,2,3,4,5
document.write(sliceArr)  //  3,4,5
```

{% hint style="info" %}
string 에도 slice 메서드가 있다

문자열을 추출할때 사용
{% endhint %}

