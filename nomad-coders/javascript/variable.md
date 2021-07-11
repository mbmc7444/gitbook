# Variable\(변수\)

### let , const , var

```text
let a = 221;
ley b =  a-5 
console.log(b) // 216
```

```text
let a = 221;
let b =  a-5 
a = 5
console.log(b,a) // 216 5
```

#### let , const의 차이

let 과 const는 재선언이 불가하다

```text
let a = 5;
let a = 3; // x

const b = 1;
const b = 2; // x
```

let 재할당 가능 , const 재할당 불가

```text
let a = 5;
a = 4; // o

const b = 2;
b =3; //x
```

#### var를 사용 하지말아야 하는 이유

```text
console.log(age);
age = 4;
var age;
```

변수를 생성하지도 값을 할당하지도 않았지만 오류가 생기지 않고 undefined가 출력된다. 유지보수가 힘들뿐더러 필요없는 변수가 생기더라도 찾을수 없을수도 있다. **let, const** 를 사용하도록 하자

