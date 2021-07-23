# 14 - References VS Copying

**Number , String 복**

```javascript
// Number

let age = 100;
let age2 = age;
console.log(age, age2); // 100, 100
age = 200;
console.log(age, age2); // 200, 100


// String

let name = 'Wes';
let name2 = name;
console.log(name, name2);
name = 'wesley';
console.log(name, name2);
```

**Array 복사**

```javascript
    const players = ['Wes', 'Sarah', 'Ryan', 'Poppy'];
    const team = players;

    console.log(players, team);
    team[3] = 'Lux';
    /*
    player  = 'Wes', 'Sarah', 'Ryan', 'Lux'
    team  = 'Wes', 'Sarah', 'Ryan', 'Lux'
    */
    
```

배열의 경우 수와 문자랑은 다르게 =으로 하게되면 복사가 아니라 참조 형태가 되기때문에 값을 바꾸게되면 기존에있단 배열도 바뀌게된다.

그렇다면 배열을 복사하는 방법은 무엇이있을까

```javascript
const team2 = players.slice();
const team3 = [].concat(players);
const team4 = [...players]; // 스프레드 연산자
const team5 = Array.from(players);
```

위의 4가지 방법으로 복사가 가능하다. slice\(\) , concat 새로운 배열로 반환되기때문에 사용 할수 있다.

**Object 복**

```javascript
 const person = {
      name: 'Wes Bos',
      age: 80
    };

   
    const captain = person;
    captain.number = 99; // 새로운 값을 대입

 
    const cap2 = Object.assign({}, person, { number: 99, age: 12 });
    console.log(cap2);
    
```

```javascript
Object.assign({newObject} , Object {key:value})
```

객체의 경우도 배열과 마찬가지로 참조가 이루워지기 때문에 그냥 복사 할수없다. 방법은 **Object.assign** 메소드를 이용하여 복사를 하면된다.

```javascript
const zini = {
  name: "Zini",
  age: 24,
  social: {
    github: "zinirun",
    instagram: "@normalzini",
  },
};
```

위의 경우는 어떨까 만약 name , age를 바꾸고 싶다면 그대로 assign 을 사용하면 된다 그러나 social 안의 값을 바꾸게되면 참조가 이루어지게되어 배열 자체가 업데이트 되버린다. 그렇기때문에 다른방법을 이용해야한다.

```javascript
    const dev2 = JSON.parse(JSON.stringify(wes));
```

JSON.parse\(\) : JSON 문자열 JavaScript 값이나 객체로 변 

JSON.stringify\(\) : json 객체를 String 객체로 변환시

