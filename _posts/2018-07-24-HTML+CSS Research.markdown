---
layout: post
title: "HTML+CSS structure"
subtitle: <span class="evidence">HTML5 구조와 CSS3 구조 공부.</span>
date: 2017-09-05
author: NoonGam
category: HTML
tags: CSS HTML
comments: true
finished: true
---


## HTML 이란 ?

![codes](/img/2018-07-24-HTML+CSS Research/1.jpg)
> 위와 같은 구조를 HTML5의 시맨틱 태그로 레이아웃을 만들었다고 한다.

소스 날라감...와.....


### css를 적용할때는 div를 사용한다

<style>
#wrapper {
  width: 100px;
  font-weight: bold;
  font-size: 20px;
}
</style>

- 사용할떄는
<div id="wrapper">
    가즈아!!!!
</div>



### p 태그
- p태그는 텍스트 단락을 만드는 용도로 앞 뒤로 줄바꿈이 일어남.
- CSS를 이용하여 텍스트 서식을 손쉽게 조절 가능.


### 형관펜
- <mark> 내용 </mark>

<style>
mark {
  background-color:lime;
  font-weight:bold;
}
</style>

.accent{
  background-color:rgba(255,0,0,0.2);
}
</style>


<mark> 입실 시간은 1시 </mark>
<p class="accent"> 퇴실 시간은 밤11시 </p>


## Ruby태그
- 일본어를 사용하기위한 태그방법으로, 가타카나나 히라가나로 표시하기위한 방법

    <ruby>
      (안녕?)<rt>hello</rt>
      </ruby>




## span 태그
- 줄바꿈 없이 텍스트 영역 한 부분을 묶어서 스타일 적용하려할때 쓰임
<span style="color:blue"> 내용 </span>
<span class="evidence"> 내용 </span>


## ul-li 목록 태그
- 목록을 만들때는 ul(순서대로)표시와 li태그를 통해 각 항목을 표시

<ul>
      <li> 내용 </li>
      <li> 내용2 </li>
      <li> 내용3 </li>
</ul>



-------
- 목록 표시를 ㅁ사각형으로 하고싶을때

<style>
ul {
      list-style-type :square;
    }
</style>

<ul>
      <li> 내용 </li>
      <li> 내용2 </li>
      <li> 내용3 </li>
</ul>




## ol-li 태그
- li의 순서대로 번호가 매겨짐.

<ol>
      <li> 내용 </li>
      <li> 내용2 </li>
      <li> 내용3 </li>
</ol>

-------------
- 로마문자로 순서 표시
<ol type="I" start="1">
  <li>첫번째</li>
  <li>두번쨰</li>
  <li>세번째</li>
</ol>

## dt dd 태그
- 타이틀과 설명을 나타내는 태그

<dt>방 종류</dt>
<dd>스위트룸</dd>
<dd>게스트룸</dd>
<dd>비지니스룸</dd>

<dt>포함 목록</dt>
<dd>드라이기</dd>
<dd>냉장고</dd>
<dd>싱글침대</dd>

## 테이블 태그
<table>
  <tr>
    <th>1행 1열</th>
    <th>1행 2열</th>
  </tr>  
    <tr>
      <td>2행 1열</td>
      <td>2행 2열</td>
    </tr>
      <tr>
        <td>3행 1열</td>
        <td>3행 2열</td>
      </tr>
      <tr>
        <td colspan="2">4행 1열</td>
        <td>4행 2열</td>
      </tr>

</table>

- 행 열 합치기
<td rowspan="2"> 내용 </td>
<td colspan="2"> 내용 </td>

2개의 행을 합친다.



## a태그
- 이미지나 링크를 연결하기 !
- 항목 연결하는 링크 만들기 !

	<a name="top"></a>
      내용 ~

  <a href="#top" class="link1"><p>[위로 가기]</p></a>
    위의 링크를 누르면 해당 name항목으로 이동


<mar>< 전체적인 틀 > </marK>
1. nav 네비게이션을 통해 각 list 생성
<nav>
  <ul>
    <li><a href="#usage">이용 안내</a></li>
    <li><a href="#reserve">예약 방법</a></li>
    <li><a href="#fee">이용 요금</a></li>
  </ul>
</nav>    

2. 아래와같이 해당 라인에 아래와 같은 a태그를 사용하여
<a name="usage"><h3>이용 안내</h3></a>
  <a name="reserve"><h3>예약 방법</h3></a>
      <a name="fee"><h3>이용 요금</h3></a>



## form 태그
- 텍스트 상자, 버튼, 목록 등 웹사이트로 어떠한 정보를 전송 목적

<form action="register.php" method="post">
post방식으로 register.php를 실행한다.

- 로그인 form창 예시
<form>
      <fieldset>
      	<legend>로그인 정보</legend>
        <ul>
			    <li>
            <label>아이디(6자 이상)<input type="text" id="id"></label>
          </li>
        	<li>
           	<label>비밀번호<input type="password" id="pw1"></label>
          </li>
        	<li>
        	 	<label>비밀번호(확인)<input type="password" id="pw2"></label>
          </li>  
        </ul>
      </fieldset>
      <fieldset>
      	<legend>개인 정보</legend>
        <ul>
	        <li><label>이름 <input type="text" id="name"></label></li>
	        <li><label>이메일 주소 <input type="email" id="email"></label></li>
		    <li>...</li>
       </ul>
      </fieldset>
</form>

------------

- 라디오 버튼

<form>
    <fieldset id="register">
    <legend>수강 과목을 선택하세요 <small>(1과목 선택 가능)</small></legend>
    	<ul>  
	        <li>
                <label><input type="radio" name="spk" id="spk" value="low" checked>영어 회화(초급)</label>
			</li>
			<li>
                <label><input type="radio" name="spk" id="spk" value="middle">영어 회화(중급)</label>
			</li>
			<li>
                <label><input type="radio" name="spk" id="spk" value="high">영어 회화(고급)</label>
            </li>        
		</ul>
     </fieldset>
  </form>

-----------

- 체크 버튼

  <form>
     <fieldset>
      <legend for="pre"> 관심분야는? <small>(다수 선택 가능)</small></legend>
       	<ul>
	       	<li>
			    	<input type="checkbox" name="pre" id="pre"  value="grammar">문법
			    </li>
			    <li>
            <input type="checkbox" name="pre" id="pre"  value="voca">어휘
			    </li>
			    <li>
            <input type="checkbox" name="pre" id="pre"  value="grammar">회화
			    </li>
			    <li>
            <input type="checkbox" name="pre" id="pre"  value="listening">리스닝
			    </li>
		    	<li>
            <input type="checkbox" name="pre" id="pre"  value="news">뉴스 청취
		    	</li>
		    	<li>
           <input type="checkbox" name="pre" id="pre"  value="reading">독해                
          </li>
        </ul>	 
	    </fieldset>
  </form>



## CSS에 대해서 드디어 알아보자...
- CSS는 디자인 부분인데 HTML과 분리하여 편하게 보기위해서
1. style.css파일을 만들고, 내부에
 my_h1_style{
   color:blue;
   font-size: 10px;
 }

2. <head>부분에 <link href="style.css" rel="stylesheet" type="text/css"></link>

3. 이제 쓰면된다.




-----------
- 스타일에는 우선순위가 존재
기본적으로는 중복된 스타일 이름은 제일 마지막에 선언된 스타일이 적용된다.
하지만 초반에 내부에
.accent {
  color:red;
  !important;
}
이렇게 !important라고 선언하면 순서에 상관없이 무조건 이 스타일이 적용됨.


## 선택자
- 전체 선택자 : 모든 페이지에 적용

\*{
  margin:10px;
  padding:10px;
  font-family: "Sans-serif"
}

- 태그 선택자 : 해당 태그는 해당 스타일 적용
p{
  font-size:12px
}


- <a>클래스 선택자 : 같은 태그라도 다른 스타일을 적용하고 싶다면 class 선택자를 통해서 예외 스타일 적용 가능 </a>
.redanccent{
  color:red;
  font-size:100px;
}

<p class="redaccent">이 내용은 100px에 red스타일이 적용됩니다.</p>

- id 선택자 : 클래스 선택자는 문서안에서 여러번 반복해서 적용 가능하지만,
id 선택자는 요소,크기,위치 등 레이아웃 지정용으로 주로 사용하기떄문에 문서안에서 한번만 적용됨

\#mynav{
  color:blue;
}

<ul id="mynav">
    <li>메뉴1</li>
    <li>메뉴2</li>
</ul>


- 하위 선택자 : 상위 요소의 하위 요소에 스타일 적용
section p {
  color:blue;
}
section태그(상위)의 p태그(하위)

- 자식 선택자 : 하위 요소 모두에게 적용되지않고, 바로 아래 자식에게만 적용

section > p {
  color:blue;
}
section태그(상위)의 p태그(자식)만 적용

- 그룹 선택자
a , p{
  color:red;
}
a태그 p태그를 red로 스타일 설정


- 속성 선택자

a[href] {
  color:blue;
}
a태그에서 href 속성을 가지고있는 태그만 적용
