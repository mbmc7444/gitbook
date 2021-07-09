# splice\(\)

배열의 기존 요소를 삭제 또는 교체하거나 새 요소를 추가하여 배열의 내용을 변경

splice\(start\[, deleteCount\[, item1\[, item2\[, ...\]\]\]\]\)

* start :  시작\(어디서부터\)
* deleteCount : 몇개를 삭제할것인지 \(0 - 아무것도 삭제하지않음 1 이상 - 갯수만큼 삭제\)
* item :무엇을 추가할지

```text
const arr = [1,2,3,4,5];

let spliceArr = arr.splice(0,2,"추가") 

document.write(arr) // 추가,3,4,5
// 0번째 자리부터 2개를 삭제하고 추가를 넣어주세요 
```

[https://im-developer.tistory.com/103](https://im-developer.tistory.com/103)

