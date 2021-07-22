# 07 - Array Cardio Day 2



```javascript
const people = [
  { name: 'Wes', year: 1988 },
  { name: 'Kait', year: 1986 },
  { name: 'Irv', year: 1970 },
  { name: 'Lux', year: 2015 }
];

const comments = [
  { text: 'Love this!', id: 523423 },
  { text: 'Super good', id: 823423 },
  { text: 'You are the best', id: 2039842 },
  { text: 'Ramen is my fav food ever', id: 123523 },
  { text: 'Nice Nice Nice!', id: 542328 }
];

// Some()
// const isAdult = people.some(function(person) {
//   const currentYear = (new Date()).getFullYear();
//   if(currentYear - person.year >= 19) {
//     return true;
//   }
// });

const isAdult = people.some(person => ((new Date()).getFullYear()) - person.year >= 19);

console.log({isAdult});

//every()
const allAdults = people.every(person => ((new Date()).getFullYear()) - person.year >= 19);
console.log({allAdults});

// find()

const comment = comments.find(comment => comment.id === 823423);

console.log(comment);

// findIndex()
const index = comments.findIndex(comment => comment.id === 823423);
console.log(index);

// splice(index, 1);

const newComments = [
  ...comments.slice(0, index),
  ...comments.slice(index + 1)
];
```

#### some\(\)

메서드는 배열 안의 어떤 요소라도 주어진 판별 함수를 통과하는지 테스트

```javascript
const array = [1, 2, 3, 4, 5];
const even = (element) => element % 2 === 0;
console.log(array.some(even));
// 인자 하나라도 true이면 true 를 리턴해준다
```

**every\(\)**

메서드는 배열 안의 어떤 요소라도 주어진 판별 함수를 통과하는지 테스트

```javascript
const isBelowThreshold = (currentValue) => currentValue < 40;

const array1 = [1, 30, 39, 29, 10, 13];

console.log(array1.every(isBelowThreshold));
// true
// 인자 하나라도 false이면 false 를 리턴해준다
```

#### find\(\)

주어진 판별 함수를 만족하는 요소를 반환

* **첫 번째 요소**의 **값**을 반환한다.
* 만족하는 요소가 없다면 **undefinde** 를 반환한다.

```javascript
const array1 = [5, 12, 8, 130, 44];

const found = array1.find(element => element > 10);

console.log(found);
// 12
```

#### findIndex\(\)

주어진 판별 함수를 만족하는 요소의 index를 반환

* **첫 번째 요소**의 **index**을 반환한다.
* 만족하는 요소가 없다면 **-1**을 반환한다.

```javascript
const array1 = [5, 12, 8, 130, 44];

const isLargeNumber = (element) => element > 13;

console.log(array1.findIndex(isLargeNumber));
//3

```

1\) .splice\(\) 를 쓸 수도 있고,  // 코드에서는 index 배열 원소부터 1개 제거하라는 것

2\) .slice\(\) 를 잘 활용하는 방법도 있다. 이 경우 원본 배열이 온전하다는 장점이 있다.

#### splice\(\)

기존 요소를 삭제 또는 교체하거나 새 요소를 추가하여 배열의 내용을 변경

#### slice\(\)

문자열의 일부를 추출하면서 새로운 문자열을 반환

```javascript
str.slice(beginIndex[, endIndex]) 
/*
beginIndex 부터 endIndex 는 미포함하여 추출 하여 반환
기존의 배열을 바꾸지 않고 새로운 배열을 만든다
*/

```

