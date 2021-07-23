# 12 - Key Sequence Detection

```javascript
const pressed = [];
const secretCode = 'wesbos';

window.addEventListener('keyup', (e) => {
  console.log(e.key);
  pressed.push(e.key);
  pressed.splice(-secretCode.length - 1, pressed.length - secretCode.length);
  if (pressed.join('').includes(secretCode)) {
    console.log('DING DING!');
    cornify_add();
  }
  console.log(pressed);
});
```

#### splice\(a,b,c\) 



메서드는 배열의 기존 요소를 삭제 또는 교체하거나 새 요소를 추가하여 배열의 내용을 변경

```javascript
pressed.splice(-secretCode.length - 1, pressed.length - secretCode.length);
```

keyup으로 생성된 배열에  secretCode와 비교하는 구문인데,  우선 굳이 저런방법을 사용해야하나 싶기도 했다. 해석하자면 

-secretCode.length = -6 , 

pressed.length = 작성된 갯수\(-7,자리부터 삭제를 한다고했으니 최대 7까지 증\)

splice\(-7 , 1\) : 첫번째 인자가 음수가 되면 배열의 마지막부터 시작이된다는 뜻이다 즉 -7이에 1이면 맨앞자리에 1자리 숫자를 삭제한다는 뜻이다.

```javascript
  if (pressed.length > secretCode.length) {
    pressed.splice(0, 1);
  }
  //알아보더중 이렇게 하면 똑같이 실행이된다.
```

좀더 깊게 생각하면 push\(\)들어간 배열이기때문에 배열 뒤에 계속해서 붙게된다 그렇기때문에 -7번째라고 코드를 작성한거 같다.

\*\*\*\*

**join\(\)**

배열의 모든 요소를 연결해 하나의 문자열로 만들어준다.

