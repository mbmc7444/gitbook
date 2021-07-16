# weather 구현

#### fatch

api를 불러오고, 정보를 내보내 주기도 하는 함수이다.

{% hint style="info" %}
&units=metric  url에 화씨를 섭씨로 바꿀때 사용 
{% endhint %}

```javascript
// https://api.openweathermap.org/data/2.5/weather?lat=37.5059673&lon=126.8784784&appid=
const API_KEY = "5d5d08f6e00bcf300b39d748a81ab0a0";

//lat=37.5059673 lon = 126.8784784
function onGeoOk(position) {
    const lat = position.coords.latitude;
    const lng = position.coords.longitude;
    console.log(lat, lng)
    const url = `https://api.openweathermap.org/data/2.5/weather?lat=${lat}&lon=${lng}&appid=${API_KEY}&units=metric`
    console.log(url)
    fetch(url).then(res => res.json()).then(data => {
        const weather = document.querySelector("#weather span:first-child")
        const city = document.querySelector("#weather span:last-child")
        console.log(city)
        city.innerText = data.name;
       weather.innerText = `${data.weather[0].main} / ${data.main.temp}`
    });
}
function onGeoError() {
    alert("Can't find you. No weather for you.");
}


navigator.geolocation.getCurrentPosition(onGeoOk, onGeoError);
     //모든 좌표를 보내준다
```

