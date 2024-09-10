# 2024_2_WebProgramming
2024_2학기 2학년 웹프로그래밍 수업

----------------------------------------------------------------------------

## Day 1 / 2024.09.04

범위: web2024_1장 p.15~

### [p.15]   
가장 윗줄(`<!doctype html>`)은 항상 적는 것. html5라는 의미    

`<!-- -->` 는 주석이라는 의미  

꺽쇠열고 첫번째로 나오는 단어가 태그.  
태그는 1. 시작과 끝이 정확한 짝지태그(body-body, head-head) 2. 하나만 존재하는 솔로태그(`<meta ~~~>`) 2가지가 존재함.  

이번 학기에는 `<html> ~ <head> ... </head> <body> ... </body> ~ </html>` 로 구성된 코드를 사용함. 크게 html 안에 head와 body로 나누어 작성함.  
body에 적은 것들은 화면에 그대로 나오고, head는 눈에 보이지 않지만 정보를 담고 있는 부분. 이번 학기에는 head 안에는 meta, title, style 3가지 태그만 사용함  

html은 컴파일 단계 없다. 문법이 틀리면 화면이 이상하게 나옴. 예를 들어 title 뒤에 /를 제외하고 적으면 title 뒤의 모든 입력값을 제목에 욱여넣음  

### [p.16]  
h2 (짝지태그)는 글자크기 설정. 1~6. 1이 가장 큼  
hr (솔로태그)는 가로줄  
br (솔로태그)는 줄바꿈, 다만 h2나 hr은 이미 한줄 의미라 줄바꿈이 자동으로 됨  

아무리 스페이스 사용해도 한 칸만 띄워짐
  
### [p.17]  
a (짝지태그) 링크 의미함.   
`<a href="2.html"> 로그인 </a>` 의 형태  
a 는 태그, 그 뒤의 href 는 속성, "2.html"는 속성 값이다.   
a의 target 속성의 _blank는 새탭에서 열리는 것을 의미, target 없으면 그냥 해당 탭에서 그 링크로 이동.  
&nbsp; 는 공백(스페이스) 의미함.(non-breaking space)  
https:// 빼먹지 말고 사용해야 함. 사이트 주소로 이동할 경우와 다른 파일로 갈 경우랑 달라야하기 때문.  

### [p.18]  
style (짝지태그) 는 디자인을 담당함.  
`<style> a { margin-right : 40px; } </style>`에서 모든 a 태그에 대해 오른쪽에 여백을 40px만큼 부여한다는 의미.  
위의 &nbsp;는 코드가 너무 지저분해지므로 이렇게 사용함.  
margin말고 padding도 존재. margin은 진짜 빈 공간, padding은 빈 공간으로 보이지만, 실제로는 크기가 커짐. 빈 공간 누르면 padding은 동작하고, margin은 동작하지 않음.  
  
### [p.19]  
2.html 만들고 1.html 새로고침 후 로그인 클릭하면 화면이 2.html로 넘어감  
css 넣는 방법: 1. head의 style 태그에 전부 넣음 (대세) 2. body의 각 태그에 style 속성 넣음  
`<body style="background-color:silver">`으로 배경을 회색으로 지정  
`<strong>아이디와 비밀번호를 입력하세요</strong>` strong은 글자 진하게 표현  

`아이디: <input type="text" name="id"> <br>
비밀번호: <input type="password" name="pw">`
input 태그는 입력 의미, type 속성은 text는 문자열, password는 화면에 나올때에 점으로 표현됨. type은 근본적으로 같음.  
name 속성은 서버로 데이터를 보낼 대에 연동되어 굉장히 중요함.  
데이터를 서버로 보내려면 name 변수가 반드시 있어야 한다.

----------------------------------------------------------------------------

## Day 2 / 2024.09.10

범위: web2024_1장 p.20~

### [p.20]
`<p> </p>`(짝지 태그) 은 문단 의미. 위아래로 조금의 간격

`<form action="" method="" > </form>` (짝지 태그) 는 서버로 보낼 데이터의 범위를 설정. 이걸로 묶어야 데이터들을 서버로 보낼 수 있다. 최소한 id, pw, 버튼(확인) 까지는 form 안에 존재해야 서버와 상호작용이 가능함

이번 학기에 form 안에 들어갈 함수 2개는 action, method.
action="여기" 에는 서버로의 목적지 주소가 들어간다. (where)
method="여기" 에는 전송 방법을 의미한다. (how) - get, post 등 (default 비어있으면: get)
get은 옮길 때에 전부에게 보이게 전송되고, post는 눈에 보이지 않게 전송된다.
보안을 생각하면 post를 사용한 상태에서 보안 조치를 취해야한다.

form, acton, method, name : 이 4가지가 중요

`<button type="submit">확인</button>` 에서 button은 누르는 버튼 만듦. type default는 submit. 짝지 태그. 
button은 위치가 중요.(form 안) 버튼 클릭 시 버튼이 속한 form을 확인하고, 그 안의 데이터를 확인해 그것을 가지고 method 방법으로 action 목적지(주소)로 간다.

### [p.21]
input type이 radio이면 name이 동일한 radio type 중에 하나만 선택 가능(복수 선택 불가능) - 동그라미로 표시되어 모든 항목 나온 상태에서 선택, value로 정해진 값이 서버로 name에 적힌 타입으로 전송됨. radio는 name, value 모두 써야 함
`<select> </select>`는 바로 되어있어서 셀렉트 바 클릭해야 항목 나오고, 거기서 선택. 선택된 값이 value가 되어 해당 name으로 그 값이 전송됨. 얘는 input 없이 자체가 select tag임. 안에 option 짝지 태그로 선택 가능한 값들을 넣을 수 있음. 각 option 태그의 뒤에 있는 `</option>` 태그는 생략 가능하다.

`<button type="submit">등록</button> <button type="reset">취소</button>`과 같이 버튼 여러 개 만들 수 있음. reset은 form 안의 입력 내용 초기화 의미함. 

글자에 하이라이트 넣고 싶으면 
위의 head 안에 style 태그 안에  `h2 {background-color: yellow; color:gray;}` 와 `strong {background-color: aqua;}` 하고 아래에 저러면 됨. 

`<h2> good morning </h2>` 
`hi <strong> hello </strong> <br>`
`good`

background가 배경색 혹은 글자 하이라이트, color는 글자색 변경