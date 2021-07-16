# background 구현

#### Math

* Math.floor\(\) : 어떤 수보다 크지 않은 최대의 정수를 반환합니다. \(내림\)
* Math.ceil\(\) : 어떤 수보다 작지 않은 최소의 정수를 반환합니다 \(올\)
* Math.round\(\): 어떤 수와 가장 가까운 정수를 반환합니다. \(반올림\)
* Math.random\(\) : 0~1 까지 랜덤으로 float형식으로  반환 ex\) 5.223235

#### createElement

요소를 추가할때 사용한다.

```javascript
const images =["img0.jpg","img1.jpg","img2.jpg","img3.jpg","img4.jpg","img5.jpg","img6.jpg",]

const chosenImage = images[Math.floor(Math.random()*images.length)]
console.log(chosenImage);

const bgImage = document.createElement("img");

bgImage.src = `../img/${chosenImage}`;
console.log(bgImage)

document.body.appendChild(bgImage)
```

