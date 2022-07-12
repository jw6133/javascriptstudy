7월 4일 12시 ~4.6
localstorage라는 공간? 저장공간이 이미 정의되어 있음. 이건 콘솔 위쪽 메뉴 중 어플리케이션-> 로컬스토리지에서 내용확인가능.
localstorage.setitem(키,키에넣을값); 로컬스토리지에 요소 추가.(저장)    ex)localstorage.setitem("username","backG");
이후 localstorage.getitem(키); 로 키에 내장되어있는 값을 불러낼 수 있음.
.removeitem(키); 로 삭제

localstorage에 값이 있으면, 이름을 기입받는 form을 보여주면 안됨. 이름이 없을때만 이름을 받아와야 하기 때문.
자주 반복되는 값은 const 변수를 지정해서 저장한 뒤 만든 변수로 반복해야지 값 여러번 호출이 안됨. 여러번 호출은 그렇게 할 필요가 없음.
그리고 그 반복되는 값이 string 이라면, const AAA_AA처럼 대문자와 언더바로 지정해두는 버릇을 들이면 좋음. 대문자+언더바는  string값이다 라는 것을 이어주면 기억하기 좋기 때문.
동일한 행위가 반복되면 그걸 함수로 만든 후 함수만 호출하면 코드가 이뻐짐.

여튼 저장하는 방법은, localstorage에 setitem으로 넣어서 저장하고,
저장한 값으로 뭘 하고싶다면, (출력하거나, 지우거나, 조건으로 걸거나) const 변수에 getitem으로 가져와서 const변수로 조작하면 됨!

7월 4일 ~5.1
4챕터 복습

clock.js 생성
interval : 아마 "주기"를 얘기하는거 같은데, 매 2초마다 실행하고 싶으면 이 2초가 interval 인터벌 이라고 하는거 같음. 아마 진짜 주기를 말하는거인듯?
인터벌 세팅 : setInterval(실행할거, 주기);  주기는 ms단위로 지정. 1000ms=1초
setTimeout(실행할거, 주기) = 인터벌이랑 하는건 비슷한데, 한번만 함. 일회용 시한폭탄?

js기본탑재인 date => new date() 이렇게 하면 현재시간 출력.
date 뒤에 .getdate .getHour .getday .getFullyear 등등으로 개별적인 요소를 integer로 받아올 수 있다.
이걸 `${}`로 붙이고 인터벌로 1초마다 실행해서 html h2에 넣어주면 시계임.

7/5 ~5.2
"문자열".padStart(길이,문자열이 길이가 아닐 시 추가할 요소) => "1".padStart(2,"0"); = "1"의 길이가 2가 아니기 때문에 "앞쪽에" 0 추가 => 01
뒤쪽에 추가하는 버전은 .padEnd()

"무언가"를 문자열로 변환하고 싶을 때, => String("무언가")

7/7 ~6.1
math module => js에 기본 탑재.
math.random() * a => 0부터 a까지 숫자 랜덤 하나 출력
math.round() = 반올림 (정수로)
math.celi() = 올림 (정수로)
math.floor() = 내림 (정수로)

bgImage.src "src"=source

document.body.appendChild(); body에 요소 추가

7/8 ~7.0
복습 및 todolist 세팅

7/9 ~7.2
const li = document.createElement("li");
    const span = document.createElement("span");
    li.appendChild(span);
    span.innerText = newTodo;  => add Todolist
    
    const button = document.createElement("button");
    button.innerText="X";
    li.appendChild(button);
함수에 ()속 요소로 event를 넣어주면, 그 event에는 발동된 순간의 event가 저장된다.
즉, 여러 버튼중 하나의 버튼을 누르면 그 특정 버튼을 눌렀다는 사실에 event에 저장됨.
그럼 그 event의 dir 요소 중, path(경로)를 조사하면 어디서 발생한건지 추적이 가능.
path로 추적하지 않아도 경로의 목적지는 "target"임.
deleteTodo를 만들기 위해 알아야 할건 클릭된 버튼이 아니라 버튼의 부모. 즉 어느 li인지. => parentElement

결론적으로, 클릭된 이벤트의(event), 목적지의(target), 부모(parentElement) ====> event.target.parentElement

7/10 ~7.5 
저장 = localstorage에 저장.
JSON.stringify() = 뭐든간에 string으로 저장.
JSON.parse() = string을 object인 array로 저장.

배열.array.forEach(ㅁ); 배열속에 있는 요소 하나씩을 ㅁ에다 넣어서 실행. ㅁ은 function.
function()에 "item"을 넣으면, foreach로 넣어진 배열에 실행되고있는 argument를 하나씩 꺼내서 알려줌. function(item)

이전거도 저장하려면, 저장되는 배열을 const에서 let으로 바꿔주면됨.
