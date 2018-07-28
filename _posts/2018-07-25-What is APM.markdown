---
layout: post
title: "웹서버 APM 이란?"
subtitle: <span class="evidence">웹 서버를 개발하다보면 APM을 모르고 지나칠 수 없다.</span>
date: 2018-07-25
author: NoonGam
category: HTML
tags: PHP MySQL
comments: true
finished: true
---



## APM ?

- what is APM ? <br>

![Codes](/img/2018-07-25-What is APM/1.jpg)
> Apache + PHP + MySQL 의 줄임말이다. APM 소프트웨어가 존재하는 것이 아니라, 이 3가지가 연동되어 운영되도록 만든 환경을 APM이라고 한다. Apache와 MySQL이 PHP와 호환성이 좋기 때문에 주로 세 프로그램을 묶어 패키지 형태로 사용한다.


<br><br><br>

## Apache?

![Codes](/img/2018-07-25-What is APM/2.png)
> 정식 명칭 : Apache HTTP server
웹 서버 프로그램이다. 웹 서버란 웹 서비스를 제공해주는 서버인데, 예를 들어 사용자가 사이트에 접속하면 웹 서버에게 HTML 파일을 요청한다. 요청을 받은 웹 서버는 클라이언트 컴퓨터에 HTML 파일을 제공하면서 사용자는 화면으로 웹 페이지를 볼 수 있게 된다.

<br><br><br>

## PHP

![Codes](/img/2018-07-25-What is APM/6.png)

> Personal Home Page의 약자로, 통칭 PHP:Hypertext Preprocessor 라고 부른다.
웹 프로그래밍 언어로, 서버에서 실행되는 언어이다. HTML의 경우 웹브라우저에서 소스를 해석해 보여주지만, PHP 는 서버에서 해석하여 HTML 코드로 만들어 브라우저에게 전달하는 것이다.

- PHP는 Apache라는 웹서버 프로그램과 연동하여 동작합니다.

- PHP는 .php파일을 처리하고, Apache는 HTML파일을 처리합니다.

- PHP를 활용하여 Dynamic(동적)웹 페이지를 만들 수 있습니다.

- 이 외에도 JSP , ASP 등 사용되고 있습니다.

- ex)예제 소스
```java
<?php
    echo $_SERVER['HTTP_USER_AGENT'];
?>
```
<br><br>

### 장점

- 웹에 최적화된 언어

- 웹개발에 필요한 수많은 로직들이 함수의 형태로 제공됨

- 크로스플랫폼

- 거의 모든 데이터베이스를 지원

- 가장 많은 공개소프트웨어가 PHP로 만들어짐


현재는 객체 기반의 Node.js,javascript와 함께 ASP , JSP등 좋은 서버 언어가 많이 생겨났지만, PHP는 가장 기본적이면서도 전세계에서 아직도 가장 많이 쓰이는 언어이다. 
<br><br><br>

## MySQL (!=MariaDB)

![Codes](/img/2018-07-25-What is APM/5.jpg)

> SQL 데이터베이스 서버이다. MySQL 없이 PHP 만으로도 간단한 웹페이지를 만드는 것은 가능하다. 하지만 웹페이지에 사진, 동영상, 게시판 등 훨씬 많은 데이터들을 저장하고 보여주고 할 때 데이터베이스와의 연동이 필요하기 때문에 MySQL을 사용하는 것이다.

MySQL은 무료이지만 기업이나 상업용으로 사용할때는 일정한 금액을 지불해야한다. 하지만 mariaDB라는 MySQL과 거의 똑같은 DBMS가 있는데 훨씬 가볍고 빠르다는 장점을 가지고 있다. 또한 MySQL을 사용하고있는 사용자도 손 쉽게 mariaDB로 변경 가능하다.<br><br>
https://mariadb.com/kb/ko/ <-- <a>한국어 메뉴얼로 제공한다.</a>

<br><br><br>

## APM 구동 원리

![Codes](/img/2018-07-25-What is APM/4.png)

> 컴퓨터 사용자(Client)가 인터넷창에서 URL을 입력하여 원하는 정보를 서버에 요청하고, 서버의 Apache 프로그램은 승인한다. 이때 포트는 80번 포트로 웹서버로 요청하고 웹서버는 사용자에게 홈페이지 정보(HTML,CSS 등)를 날려준다.
사용자가 로그인 요청이나 다른 정보에 대한 요청을 하면 해당 정보를 제공하기 위해 웹서버는 PHP에게 스크립트 실행하기를 요청하고 PHP는 미리 작성된 프로그램을 통해 MySQL에 쿼리를 질의한다.
MySQL은 데이터베이스에 저장된 데이터를 가져와 PHP에 돌려주고 PHP는 데이터베이스에서 가져온 데이터와 PHP 코드를 모두 HTML 형태로 변경하고, 해당 HTML 파일을 Apache(웹 서버)에게 전송한다.
Apache는 완성된 HTML 파일을 클라이언트 측의 컴퓨터 웹 브라우저에 전달한다.

<br><br><br>

## 참고 자료

- http://gwonhouse.tistory.com/2 [김윤권]
- http://to-paz.tistory.com/8#comment12952368
