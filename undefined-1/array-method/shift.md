# shift\(\)

배열에서 **첫 번째** 요소를 제거하고, **제거된 요소**를 반환합니다. 이 메서드는 배열의 길이를 변하게 합니다.

```text
const arr = [0,1,2,3];

let shiftArr = arr.shift() //0

document.write(arr) // 1,2,3
```

while 반복문에서도 사용된다

```text
const arr = [0,1,2,3];

while( (i = arr.shift()) !== undefined ) {
document.write(i) // 0,1,2,3
}
document.write(arr) // ""

/*
while 문 한번 돌 때 마다 배열의 소를 제거하고, 
이는 빈 배열이 될 때까지 반복
*/
```

