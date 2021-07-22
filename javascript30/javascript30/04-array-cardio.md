# 04 - Array Cardio

```javascript
    const inventors = [
      { first: 'Albert', last: 'Einstein', year: 1879, passed: 1955 },
      { first: 'Isaac', last: 'Newton', year: 1643, passed: 1727 },
      { first: 'Galileo', last: 'Galilei', year: 1564, passed: 1642 },
      { first: 'Marie', last: 'Curie', year: 1867, passed: 1934 },
      { first: 'Johannes', last: 'Kepler', year: 1571, passed: 1630 },
      { first: 'Nicolaus', last: 'Copernicus', year: 1473, passed: 1543 },
      { first: 'Max', last: 'Planck', year: 1858, passed: 1947 },
      { first: 'Katherine', last: 'Blodgett', year: 1898, passed: 1979 },
      { first: 'Ada', last: 'Lovelace', year: 1815, passed: 1852 },
      { first: 'Sarah E.', last: 'Goode', year: 1855, passed: 1905 },
      { first: 'Lise', last: 'Meitner', year: 1878, passed: 1968 },
      { first: 'Hanna', last: 'Hammarström', year: 1829, passed: 1909 }
    ];

    const people = [
      'Bernhard, Sandra', 'Bethea, Erin', 'Becker, Carl', 'Bentsen, Lloyd', 'Beckett, Samuel', 'Blake, William', 'Berger, Ric', 'Beddoes, Mick', 'Beethoven, Ludwig',
      'Belloc, Hilaire', 'Begin, Menachem', 'Bellow, Saul', 'Benchley, Robert', 'Blair, Robert', 'Benenson, Peter', 'Benjamin, Walter', 'Berlin, Irving',
      'Benn, Tony', 'Benson, Leana', 'Bent, Silas', 'Berle, Milton', 'Berry, Halle', 'Biko, Steve', 'Beck, Glenn', 'Bergman, Ingmar', 'Black, Elk', 'Berio, Luciano',
      'Berne, Eric', 'Berra, Yogi', 'Berry, Wendell', 'Bevan, Aneurin', 'Ben-Gurion, David', 'Bevel, Ken', 'Biden, Joseph', 'Bennington, Chester', 'Bierce, Ambrose',
      'Billings, Josh', 'Birrell, Augustine', 'Blair, Tony', 'Beecher, Henry', 'Biondo, Frank'
    ];

    // filter()
    // 1. 1500 년대에 태어난 발명가 추려내기
    const fifteen = inventors.filter(inventor => (inventor.year >= 1500 && inventor.year < 1600));
    console.table(fifteen);

    // map()
    // 2. first, last 이을 배열로 뽑아내보자
    const fullNames = inventors.map(inventor => `${inventor.first} ${inventor.last}`);
    console.log(fullNames);

    // sort()
    // 3. 나이순대로 
    // const ordered = inventors.sort(function(a, b) {
    //   if(a.year > b.year) {
    //     return 1;
    //   } else {
    //     return -1;
    //   }
    // });

    const ordered = inventors.sort((a, b) => a.year > b.year ? 1 : -1);
    console.table(ordered);

    //reduce()
    // 4.  살아온 시간들의 합
    const totalYears = inventors.reduce((total, inventor) => {
      return total + (inventor.passed - inventor.year);
    }, 0);

    console.log(totalYears);

    // 5.  살아온 횟
    const oldest = inventors.sort(function (a, b) {
      const lastInventor = a.passed - a.year;
      const nextInventor = b.passed - b.year;
      return lastInventor > nextInventor ? -1 : 1;
    });
    console.table(oldest);

    // 6. 파리 길 이름중에 de 가들어간 이름 찾기 
    // https://en.wikipedia.org/wiki/Category:Boulevards_in_Paris

    // const category = document.querySelector('.mw-category');
    // const links = Array.from(category.querySelectorAll('a'));
    // const de = links
    //             .map(link => link.textContent)
    //             .filter(streetName => streetName.includes('de'));

    // 7. sort Exercise
    // last name 을 기준으로 알파벳 순
    const alpha = people.sort((lastOne, nextOne) => {
      const [aLast, aFirst] = lastOne.split(', ');
      const [bLast, bFirst] = nextOne.split(', ');
      return aLast > bLast ? 1 : -1;
    });
    console.log(alpha);

    // 8. Reduce Exercise
    // 같은 instance 의 개수를 계산해보기
    const data = ['car', 'car', 'truck', 'truck', 'bike', 'walk', 'car', 'van', 'bike', 'walk', 'car', 'van', 'car', 'truck', 'pogostick'];

    const transportation = data.reduce(function (obj, item) {
      if (!obj[item]) {
        obj[item] = 0;
      }
      obj[item]++;
      return obj;
    }, {});

    console.log(transportation);
```

#### filter\(\)

주어진 함수의 기를 통과하는 모든 요소를 모아 새로운 배열로 반환

```javascript
const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

const result = words.filter(word => word.length > 6);
/*
 words 배열 안에 글자수가 6글자 이상이되는것만 반환
 'exuberant', 'destruction', 'present'
 */

```

#### map\(\)

배열 내의 모든 요소 각각에 대하여 주어진 함수를 호출한 결과를 모아 새로운 배열을 반환

```javascript
const array1 = [1, 4, 9, 16];

const map1 = array1.map(x => x * 2);
/*
배열안에 값에 2를 곱한값을 배열로 반
2 , 6, 
*/
```

#### sort\(\)

배열의 요소를 적절한 위치에 정렬한 후 그 배열을 반환

* 첫 번째 인수가 두 번째 인수보다 작을 경우 - 값
* 두 인수가 같을 경우 0
* 첫 번째 인수가 두 번째 인수보다 클 경우 + 값

```javascript
const months = ['March', 'Jan', 'Feb', 'Dec'];
months.sort();
console.log(months);
// Dec, Feb, Jan, March

const array1 = [1, 30, 4, 21, 100000];
array1.sort();
console.log(array1);
/*
1,100000,21, 30, 4 
 숫자 순서로 배열하고싶다면
array1.sort(function(a, b) { // 오름차순
    return a - b;
    // 1, 2, 3, 4, 10, 11
});
array1.sort(function(a, b) { // 내림차
    return b - a;
    // 1, 2, 3, 4, 10, 11
});
*/

```

#### reduce\(\)

배열.reduce\(\(누적값, 현잿값, 인덱스, 요소\) =&gt; { 

return 결과 

}, 초깃값\);

```javascript
const array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
 
const initValue = 0;
 
const totalResult = array.reduce((arr, cur, idx, array) => {
    return arr + cur;
}, initValue);
/* 
0
(0+1) = 1
(1+2) = 3
(3+3) = 6
(6+4) = 10
(10+5) = 15
(15+6) = 21
(21+7) = 28
(28+8) = 36
(36+9) = 45
(45+10) = 55 
즉 (누적값 + 현재값)
*/

```

#### includes\(\)

문자열이 특정 문자열을 포함하는지 확인

```javascript
let users = [
  { id: 11, name: 'Adam', age: 23, group: 'editor' },
  { id: 47, name: 'John', age: 28, group: 'admin' },
  { id: 85, name: 'William', age: 34, group: 'editor' },
  { id: 97, name: 'Oliver', age: 28, group: 'admin' }
];
let res = users.filter(it => it.name.includes('o'));
// { id: 47, name: 'John', age: 28, group: 'admin' },
```

{% hint style="info" %}
#### Array.from\(category.querySelectorAll\('a'\)\);

배열로 바꾸는 코드\(map\(\), filter\(\) 을 사용하려면 배열이여야 가능하다\) 
{% endhint %}



