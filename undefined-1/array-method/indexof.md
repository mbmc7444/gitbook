# indexOf\(\)

배열에서 지정된 요소를 찾을 수 있는 첫 번째 인덱스를 반환하고 존재하지 않으면 -1을 반환

string.**indexOf**\(searchvalue, position\)  


* searchvalue : 필수 입력값, 찾을 문자열
* position : 선택 입력값 
  * 기본값은 0
  * string에서 searchvalue를 찾기 시작할 위치 

```text
const arr = ['c','b','a','d'];

let indexOfArr = arr.indexOf("a")  // 1
let indexOfArr = arr.indexOf("e")  // -1
```

요소의 모든 항목 찾기

```text
var indices = [];
var array = ['a', 'b', 'a', 'c', 'a', 'd'];
var element = 'a';
var idx = array.indexOf(element);
while (idx != -1) {
  indices.push(idx);
  idx = array.indexOf(element, idx + 1);
  /*
  idx는 array의 길이만큼 +1을 반복하게된다.
  즉 0 번째 짜리부터 1,2,3,4,5 자리부터 각각 찾게되는것
  첫번째 자리에 a가 있기때문에 0 그다음 +1 
  while 첫번째로 돌아가서 다음 a자릿수를 찾게된다.
  마지막에 indices 배열안에는 array안에 a의 index가 들어가게된 
  */
}
document.wrtie(indices) // [0, 2, 4]
```

