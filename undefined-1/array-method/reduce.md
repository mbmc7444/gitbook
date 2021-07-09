# reduce\(\)

배열.reduce\(\(누적값, 현잿값, 인덱스, 요소\) =&gt; { return 결과 }, 초깃값\);

```text
const arr = [1,2,3];
result = arr.reduce((acc, cur, i) => {
  document.write(acc, cur, i);
  return acc + cur;
}, 0);
/*
 0 1 0
 1 2 1
 3 3 2
 acc = 0,1,3 (누적값으로 0 시작해서 0 , 0+1, 1+2 );
 cur = 1,2,3 (배열의 값과 같다)
 i   = 0,1,2 (arr 의 index)
 */

result; // 6
```

