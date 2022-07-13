7/12 ~7.8
[{id:aaa , "text"}, {id:bbb, "text"}] =>li를 id로 구분가능해짐. => 지울때 로컬스토리지에서 뭘 지워야 할지도 알게됨.
Date.now = 1000분의 1 밀리초 제공 

array에서 뭘 지우는건, 지우는게 아니라 지울걸 제외한 새로운 array를 만드는 것임. => .filter(배열요소에 각각실행함.)
[].filter()를 사용하기 위해서는 괄호 안에 filter 함수가 있어야 함. => filter 함수를 function으로 따로 만들어야함.
여튼 filter는 true를 반환하는 요소를 그대로 유지시키고, false를 반환하는 요소는 버림. => "필터링"
결론적으로, filter function 에서 지우고싶은 요소가 false가 나오게 return값을 조정하면 됨. 예시) id가 aaa인걸 지우려면, return array.id !== "aaa"
이렇게 하면 aaa가 아닌 것들은 true를, aaa는 false를 반환해서 aaa가 없어짐.

함수 화살표 let sum = (a, b) => a + b; 은 다음과 같음.
let sum = function(a, b) {
  return a + b;
};
위의 화살표 함수를 이용하면, .filter에서 함수를 따로 만들 필요가 없음.
array.filter(item => item > 2)

7/13 ~8.1
navigator.geolocation.getCurrentPosition(a,b); => 내위치. a는 잘 작동됬을때 사용할거, b는 에러일때 쓸거 (함수)

function onGeoOk(position) {
    const lat = position.coords.latitude;
    const lng = position.coords.longitude;
    console.log("You live in", lat, lng);
  }                                                 
  
  = latitude는 위도 longitude는 경도.
  이걸 위치로 바꿔줄 api = openweathermap.org
  https://api.openweathermap.org/data/2.5/weather?lat={lat}&lon={lon}&appid={API key}
  You live in 37.5427083 127.0936762
  https://api.openweathermap.org/data/2.5/weather?lat=37.5427083&lon=127.0936762&appid=1e387d50f02e1624f01db6925218db94&units=metric
