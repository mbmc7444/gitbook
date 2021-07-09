# join\(\)

배열의 모든 요소를 연결해 하나의 문자열로 반환

```text
const arr = ['apple','lemon','banana'];

let joinArr = arr.join()  
```

```text
let joinArr1 = arr.join()  
document.write(joinArr1+'<br>') //apple,lemon,banana
let joinArr2 = arr.join(',') 
document.write(joinArr2+'<br>')//apple,lemon,banana
let joinArr3 = arr.join('+') 
document.write(joinArr3+'<br>') //apple+lemon+banana
let joinArr4 = arr.join('') 
document.write(joinArr4+'<br>') //applelemonbanana

```

