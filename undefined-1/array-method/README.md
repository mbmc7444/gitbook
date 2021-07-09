# array - method

### map 

####  :모든 요소 각각에 대하여 주어진 함수를 호출한 결과를 모아 새로운 배열을 반환

```text
const arr = [0,1,2,3];

let mapArr = arr.map(function(element){
    return element * element;
});
// 혹은 arrow 함수 가능
mapArr = arr.map(element => element * element);

document.write(mapArr); // [ 0, 1, 4, 9 ]
```

 **callback 함수 인자**

```text
const arr = [0,1,2,3];

let mapArr = arr.map(function(element, index, array){
  document.write(`${array}의 ${index}번째 인자 : ${element}`);;
 return element * element;

});

/* 
0,1,2,3의 0번째 인자 : 0
0,1,2,3의 1번째 인자 : 1
0,1,2,3의 2번째 인자 : 2
0,1,2,3의 3번째 인자 : 3
*/

/*
return 값은  
0 * 0 = 0 
1 * 1 = 1 
2 * 2 = 4
3 * 3 = 9

*/
 
```

l

