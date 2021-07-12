# Object

의미있는 데이터를 쉽게 정리할수있다.

#### Object\(객체\) 생성

```javascript
const playerName = "nico"
const playerPoints = 1212
const playerHandsome = "false"
const playerFat = "little bit"

console.log(player); // nico
console.log(player.name);// 1212
```

배열로 정리 하게되면 , nico가 무엇인지 1212가 무엇인지 확인 할수없다. 만약 배열로 정리를 해야한다면,주석으로 의미를 정의해놔야한다.

```javascript
// player[0] = name;
// player[1] =  points; 
const player = ["nico" , 1212, false, "little bit"]

```

#### 데이터 변경

```javascript
Player.handsome = true;
```

#### 데이터 추

```javascript
player.lastName: "potato";
```

#### 데이터 합산

```javascript
player.points = player.points + 15;
```

