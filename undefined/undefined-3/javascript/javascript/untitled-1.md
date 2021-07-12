# 배열

### 배열\(Array\)

연관 데이터를 모아서 묶고 관리하기 위해서 사용하는 데이터 타입

### 

#### 배열의 생

```text
var member = ['egoing', 'k8805', 'sorialgi'] 
//변수의 값들을 각각 원소(요소,Element)라 한다
//원소는 각각의 고유의 값을 갖는데 이값을 색인(index)이라한
```

#### 출

배열에 담겨있는 값을 가져올 때는 대괄호 안에 숫자\(index\)를 넣는다.

```text
alert(member[0]); // egoing
alert(member[1]); // k8805
alert(member[2]); // sorialgi
```

{% hint style="info" %}
배열을 사용하지않고 각각의 변수 값을 호출하려면 여러번  호하거나 또는 함수를 만들어야하는 비효율적인 코드를 작성하게된다
{% endhint %}

#### 배열의 사용

```text
function get_members(){
    return ['egoing', 'k8805', 'sorialgi'];
}
members = get_members();

for(i = 0; i < members.length; i++){
 
    document.write(members[i].toUpperCase());   
    document.write('<br />');
}

```

{% hint style="info" %}
toUpperCase\(\) 소문자를 대문자로 변환해다.

 내장함수 또는 사용자 정의함수라고도한다.
{% endhint %}

#### 배열의 크

length 배열의 길이를 알수있다.

```text
var arr = [1,2,3,4];

arr.length; // 4 
```

#### 배열의 조

push 배열 마지막에 원소 추가

```text
var li = ['a', 'b', 'c', 'd', 'e'];
li.push('f');
alert(li); // a,b,c,d,e,f
```

concat 배열 마지막에 여러 원소 추가

```text
var li = ['a', 'b', 'c', 'd', 'e'];
li = li.concat(['f', 'g']);
alert(li); //a,b,c,d,e,f,g
```

unshift 배열 시작부문에 원소 추

```text
var li = ['a', 'b', 'c', 'd', 'e'];
li.unshift('z');
alert(li); //z,a,b,c,d,e
```

Splice 배열의 특정구간을 추출하거나, 특정구간에 특정 배열을 추가

```text
var li = ['a', 'b', 'c', 'd', 'e'];
li.splice(2, 0, 'B'); 
alert(li);  // a ,b,B,c,d,e

// 2 = index, 0(삭제할지 않할지), B = 해당 원소를 추

// 삭제된 값도 같이 출
```

#### 배열의 제거

shift 첫번째 원소 제거

```text
var li = ['a', 'b', 'c', 'd', 'e'];
li.shift();
alert(li); // b,c,d,e
```

pop 마지막 원소 제

```text
var li = ['a', 'b', 'c', 'd', 'e'];
li.pop();
alert(li); // a,b,c,d
```

#### 배열의 정

sort 알파벳 순서로 정

```text
var li = ['c', 'e', 'a', 'b', 'd'];
li.sort();
alert(li); //a b c d e  알파벳 순서
```

reverse 알파벳 역순으로 정

```text
var li = ['c', 'e', 'a', 'b', 'd'];
li.reverse(); 알파벳 순서 역순
alert(li); // e,d,c,b,a
```

{% hint style="info" %}
Sort 를 직접 합수를 정의하고 원하는 정렬방법으로 정렬 가능하다
{% endhint %}

