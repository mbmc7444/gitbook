# 조건문의 활용

복잡하고 긴 코드를 간단하게 줄일수 있는것이 중요하다.

```text

  <input type ="button" value = "day" onclick="
    document.queryselector('body').style.backgroundColor ='white'
    document.queryselector('body').style.color = "black";
  "> 
  
  <input type ="button" value = "night" onclick="
    document.queryselector('body').style.backgroundColor ='black'
    document.queryselector('body').style.color = "white";
  "> 
```

두개의 버튼으로 되어있는 코드를 하나의 버튼으로 조건에 맞는 코드로 바꿀수있다.

```text
  <input id="night_day" type="button" value="night" onclick="
    if(document.querySelector('#night_day').value === 'night'){
      document.querySelector('body').style.backgroundColor = 'black';
      document.querySelector('body').style.color = 'white';
      document.querySelector('#night_day').value = 'day';
    } else {
      document.querySelector('body').style.backgroundColor = 'white';
      document.querySelector('body').style.color = 'black';
      document.querySelector('#night_day').value = 'night';
    }
  ">
```

night\_day라는 아이디 갖고있는 input의 value가 night라는것이

 참일경우과 거짓일경우의 실행하라는 코드이다.

