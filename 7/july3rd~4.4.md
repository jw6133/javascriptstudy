# javascriptstudy
JS nomadcoder Study

<6/27> ~2.0
readme 파일은 메모장이라고 생각하면될듯?

chrome console => ... => 도구 => 개발자 도구

HTML/CSS/JAVASCRIPT

HTML=실행파일 / CSS=옵션파일(배경색&폰트&etc...) / JS=명령어 파일

HTML에서 !하고 엔터하면 기본틀. 같은 의미로 link 하고 엔터하면 link틀 만들어짐

CSS=style&class

<6/28> ~2.8
콘솔에게 메세지 보내기 : console.log() 괄호안에는 문자나 숫자 *log는 출력하는 의미.

변수 - const : 바뀌지 않는 값(constant) non-changing "기본값"
변수2 - let : 업데이트 가능한 값
변수3 - var : 낡은 변수 (구버전 요소).무규칙 하지만 let 사용 권장.
syntax : 문법&규칙 등 언어마다 있는 구성요소

boolean: True or False and 
null~false
undifined => let something; 같이 썸띵에 값을 할당하지 않으면 말 그대로 할당되지 않은, "undifined"상태가 되는 것임.
undifined와 null은 다름. null은 정의된 공허. undifined는 정의조차 안된 공허 그 자체.

배열 : array = const A = [a,b,c,d,e]; & const party = [true, false, undefined , "back", 2, null];
배열에 추가 party.push();

object : 객체 => {}; & 하나끝날때 "," comma
const player = {
name : "back", points : 10, fat : "true"};

ㄴ> player.name = back
object properties는 나중에도 추가 가능. 선언하면 추가되는 형식. ex) player.lastname:jiwoong 하면 마지막 위치로 추가됨.
player.points = player.points+15 도 가능.

function(함수)=> .xxx(argument) *argument는 인수라고 한다.
function sayHello(name){
console.log("my name is "+name);
}
물론 fuction도 object 구성원이 가능함.

<6/29> ~3.0
복습&복습 variable to function

return : 값을 사출 (함수로부터) 리턴하면 이후 함수내용은 실행 x

conditional : 조건문
*prompt : 메세지 입력 창띄우기. prompt(message,default) => 메세지는 문자열/디폴트는 ?
메세지를 입력하면 그 값을 가짐. 19 입력시 prompt가 포함된 함수는 19를 return한다.
typeof : 자료형 반환. console.log(typeof name); 처럼 씀.
parseInt : 대상을 number로 전환. 변환시 숫자가 아닐 떄, "NaN" 숫자가 아니라는 뜻의 문자를 반환함.
isNaN(a) : a가 NaN인지 판단하여 True&False(boolean) 반환.

&& and, || or 

<6/30> ~3.2
documents : 브라우저에 내장되어있는 object (많은 내용 포함) HTML 객체임.
이것을 콘솔에선 javascript 형식으로 보여줌.
브라우저가 정보가 아주 많이 든 html object인 document를 콘솔에서 보여주는 형식임.
console에서 document 수정도 가능함.
document.title="jw6133";
|부가설명|
- document는 HTML파일을 오브젝트화 해서 JS로 가져온다
- 가져온 document에서 getElementById를 통해 HTML의 특정 element를 가져올 수 있다
- 가져온 element의 속성들을 통해 내용을 추가하거나 수정을 할 수 있다
- 
h1 id="aaa">"grab me!"</h1> => document.getElementById("aaa");

element 자세하게 => console.dir()
결론: javascript에서 HTML의 요소를 변경 가능하다

<div class = "hello">
  h1 "grab me!" </h1>
  </div>                  => document.getElementsByTagName("h1"); (class 라면 getElementsByClass.)
  
NICO's PICK : querySelector&querySelectorAll => CSS 방식으로 검색 
예시 : class hello 속의 h1태그 => querySelector(".hello h1"); (동일한거 여러개 있을 시 처음거만 나옴.)
동일한거 다 가져오고 싶을 때. => querySelectorAll
.hello h1:first-child
querySelector 에서의 id는 #을 붙어야 함. #hello

<<document.querySelector 중요>>

<7/1> ~3.8
const titles = document.querySelector("div.hello:first-child h1"); 이후 titles.style.color = "blue"; 로, html 요소를 javascript로 변환할 수 있다는 것이 강력한 요소.

console.dir 을 하면 나오는 object 중, 접두사로 on이 붙은 on~이 바로 EVENT이다.
event는 javascript가 listen 할 수 있음.

addEventListener => const요소.addEventListener("감지할 이벤트",감지했을 때 할거);
title.onclick=handleTitleClick; = title.addEventListener("click",handleTitleClick);
단 NICO는 addeventlistener를 선호함.
*이벤트 찾는 법*
예시) h1 html element mdn => html의 h1에 연계가능한 이벤트를 MDN에서 찾는다(구글링). Mozila Developing Network
그럼 MDN 사이트 중 "Web Api"라고 써져있는 사이트에 들어간다.
그럼 Event 섹터에 있음.

다른 방법 : console.dir()로 properties를 살펴보면 사용가능한 event 목록이 나옴 (on으로 시작하고 null로 되있을거임)
document는 div 가져오기가 안됨. document는 필수요소인 body/head/title 등이 됨.

if else문에서 조건을 걸때 =는 3개 써야함. if(h1.style.color==="blue")

css에서 클래스 생성 => .클래스 ex).active{ }

js로 class 이름 변경은 안하는게 좋음 => 많은 버그
변경방법 : classList
toggle : class 가 존재하는지 확인. 존재하면, 삭제. 존재하지 않으면, 추가.
 if(h1.classList.contains(clickedClass)){
     h1.classList.remove(clickedClass);
    }
    else{
        h1.classList.add(clickedClass); 
    }                                                  => toggle 하나로 끝.  -> h1.classList.toggle("clicked");

<7/2> ~4.4
html에  <input type="text" placeholder=="What is your name?"> 생성하면 쓸수있는 칸이 나옴.
이걸 div에 포함시켜서 js에서 div를 목표로 서치해서 가져오면, 안에 입력한 값을 function을 통해 조정할 수 있다. 위에서 한 clickevent같은걸로.
물론 클릭할 버튼 <button>aaa</button>은 따로 만들어야 한다.

길이 구하기 => 구하기.length

<input>을 <form> 안에 넣어야 값이 무조건 필요하다는 조건이 발현됨. (기본탑재) -> 단, 새로고침됨. 버튼 누를때마다. (버튼은  input의 value을 사용함. 그것이 새로고침을 이끌어냄.)

form 안에서 enter를 누르고 input이 더는 존재하지 않으면 자동으로 submit되는 규칙 => data를 기억하게 하려면, 이것을 막아야 함. (새로고침을 유발하기 때문.
function에 () 추가시 바로 실행에 들어감. (중요!)

(더많이중요!) js는 eventListener function을 실행할 때. 곧이곧대로 실행하지 않는다.
burster() 함수가 있다면, js는 이 함수에 첫번째 인수에 나에게 도움을 줄만한 정보를 포함해서 함수를 호출한다고 한다. 
burster("aaa")로 실행한다고 이해? 하면 될듯
이 도움을 줄만한 정보는, 함수에서 일어난 일에 대한 세부정보 (믿을만한지 boolean, 명령타입이 뭔지, 명령의 타겟은뭔지.. 등등 진짜 세부정보.)
.preventDefault() 는 function이 기본적으로 실행하는 일을 막아줌. (기본적으로 submit하면 새로고침을 하는데, 그런걸 막아주는거같음.)

여튼 그래서 이벤트리스너에 함수호출할때, 함수에다가 임의의 인수를 넣지 않아도 될때 넣으면, 함수 이벤트에 대한 TMI를 넣어서 내가 쓸수 있게 하는 거 같음.
물론 인수 안넣으면 안받는거고, 넣으면 받는거고. 이 TMI는 내가 또 쓸수도 있겠다. 이 첫 인수는 "event"라고 명칭하는게 관행이라고 함.

여튼 기억하기 위한 조건인 129줄의 조건은 .preventDefault이고, 적용 후 원래대로 value를 받아 출력하면 목표가 달성된다.

alert는 모든것을 멈춤. 하지만 alert를 확인버튼 눌러서 끄면 킵고잉.
이 TMI 중 "path"라는 부분을 보면, 이 이벤트가 어떤 과정을 통해 실행되는지 나옴. 역순으로. ex) a,body,html,document,Windows => 윈도우의 document속 html속 body의 a로 실행.

css로 숨기기 => display:none

문자열을 저장하는 변수는 전부 대문자에 _로 이어서 만드는 관행이 있음.

문자열 작성 팁
greeting.innerText = "hello "+username; 이랑 
greeting.innerText = `Hello ${username}; 은 같음. `문자열 ${변수명}` 단, ""는 쓰면 안됨. "" 쓸거면 +쓰세용 `이거는 ~ 이랑 같이있는거임. 메이플 캐시샵
