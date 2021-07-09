# concat\(\)

인자로 주어진 배열이나 값들을 기존 배열에 합쳐서 새 배열을 반환

```text
const arr = [1,2,3,4,5];
const addarr = [6,7,8]

let concatArr = arr.concat(addarr)

document.write(arr) // 1,2,3,4,5
document.write(concatArr) // 1,2,3,4,5,6,7,8
```

3개의 배열 합치기

```text
const arr = [1,2,3,4,5];
const addarr = [6,7,8]
const addarr2 = [9,10]

let concatArr = arr.concat(addarr,addarr2)
// 1,2,3,4,5,6,7,8,9,10
```

배열 이어 붙이기

```text
const arr = [1,2,3,4,5];

let concatArr = arr.concat(6, [7, 8]);
// 1,2,3,4,5,6,7,8
```

