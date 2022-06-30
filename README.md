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

<6/30>
documents : 브라우저에 내장되어있는 object (많은 내용 포함) HTML 객체임.
이것을 콘솔에선 javascript 형식으로 보여줌.
브라우저가 정보가 아주 많이 든 html object인 document를 콘솔에서 보여주는 형식임.
console에서 document 수정도 가능함.
document.title="jw6133";

//<h1 id="aaa">"grab me!"</h1> => document.getElementById("aaa");
