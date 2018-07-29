---
layout: post
title: "ICT 안드로이드 차세대 언어 코틀린 Kotlin 세미나 출장"
subtitle: <span class="evidence"> Java에서 Kotlin으로 넘어가는 안드로이드? </span>
date: 2018-07-09
author: NoonGam
category: Android
tags: Kotlin Language
comments: true
finished: true
---

## 2018 ICT 코틀린 세미나

일시 : 2018-07-26 13:00 ~ 18:00
장소 : 서울대학교 SK Tacademy


- 안드로이드 앱 개발 코틀린 세미나

![Codes](/img/2018-07-26-ICT 세미나 안드로이드 코틀린Kotlin 출장/111.jpg)

> 연구 과제에 안드로이드 앱의 적용 가능성과 개발 언어, 현황 등 파악하기 위해 코틀린 관련 세미나에 참가하게 되었습니다.

<br>



![Codes](/img/2018-07-26-ICT 세미나 안드로이드 코틀린Kotlin 출장/222.jpg)

> 이번 ICT 코틀린 세미나는 서울대학교 Tacademy에서 하기때문에
아침 일찍 SRT 고속열차를 타고 올라갔습니다.
대전 -> 서울 약 50분 소요

<br>


![Codes](/img/2018-07-26-ICT 세미나 안드로이드 코틀린Kotlin 출장/333.jpg)

> 입구 사진

<br>


![Codes](/img/2018-07-26-ICT 세미나 안드로이드 코틀린Kotlin 출장/2.jpg)

> 세미나실 입구

<br>

![Codes](/img/2018-07-26-ICT 세미나 안드로이드 코틀린Kotlin 출장/444.jpg)

> 미리와서 기본 세팅과 프로그램 설치를 진행하였습니다.  

<br>

![Codes](/img/2018-07-26-ICT 세미나 안드로이드 코틀린Kotlin 출장/555.jpg)

> 김태환 개발자님의 프레젠테이션

<br>

<br>


## 설치 정보
  - Android Studio 3.0 이상
  - 코틀린 버전 1.2.51 이상

  gradle scripte -> build.gradle(project) -> ext.kotlin_version = '1.2.51'으로 설정.



## 코틀린 특징

- Null safe의 특징을 통해서 자주 발생하는 NullException을 예방할 수 있다.
- 기본적으로 객체지향언어이지만, 람다 표현식과 같은 함수형 프로그래밍의 컨셉을 가지고 있다.
- 정적인 프로그래밍 언어
- JVM 위에서 작동되는 언어
- Jetbrain 개발
- Javascript를 지원한다
- 자바에서 코틀린 사용가능하고 코틀린에서 자바 사용을 가능하다.
- getter , setter가 존재하지 않음.(하지만 자체적으로 비슷한 기능을 지원함)
- null값을 지원하지않음.
  >  var variable : String<a>?</a> = "a"
     variable = null;
    위와 같이 물음표를 써야 null 사용 가능.

- Java는 클래스 생성시에 default로 클래스 범위가 정해지는데
Kotlin은 클래스 범위 선언 안해도 자동으로 전역변수가 된다==private가없다.
- 1 개의 primary constructor
- N 개의 secondary constructor
- secondary constructor에서는 primary constructor 호출해야 한다.

<span class="evidence"> Kotlin언어로 개발된 프로그램이 Java로 자동 변경 가능하며, Java로 개발된 프로그램이 Kotlin언어로 변환이 가능하다.</span>

## 코틀린 세미나 후기

![Codes](/img/2018-07-26-ICT 세미나 안드로이드 코틀린Kotlin 출장/123.png)

> 정말 많은 대학생,대학원,기업체, 교수분들이 오셔서 서로 대화를 하였으며, 세미나 진행중에 궁금한점이나 문제점이 생기면 카카오톡 오픈채팅방을 통해서 바로바로 물어보고 답변을 들을 수 있었다.
지금까지 봐왔던 세미나보다 참여율이 좋았고, 세미나 수준도 높았다.  

<br>

1. 확실히 안드로이드 스튜디오에서 Java를 통해서 많이 개발해 봤지만, 속도면에서 매우 빨랐다.
2. Java로 개발한 코드가 Kotlin으로 변환하면 필요없는 부분을 빠르게 생략해주고, 코드를 직관적으로 줄여줘서 좋다.
3. Android Studio에서 100% 상호 호완기능을 통해서 편리하게 사용할 수 있었다.

<a>
그래도 아직은 커뮤니티 부족으로 계속 컨트리뷰터로 활동하거나 지속적으로 관심을 가지고 따라온 개발자가 아니라면
진입장벽이 아직 높다. 또한 Kotlin으로 변환하여도 아직 버그나 오류가 생겨서 개발자가 다시 수정해줘야 하는 번거로움이 있다.
</a>

## 안드로이드 코틀린 개발 및 적용 중인 회사들


![Codes](/img/2018-07-26-ICT 세미나 안드로이드 코틀린Kotlin 출장/1.PNG)

<br><br><br>


## 코틀린으로 개발한 앱

- https://github.com/wodonggun/Kotlin_GitApp [wodonggun github]




![Codes](/img/2018-07-26-ICT 세미나 안드로이드 차세대 언어 코틀린Kotlin/2.jpg)
![Codes](/img/2018-07-26-ICT 세미나 안드로이드 차세대 언어 코틀린Kotlin/3.jpg)

![Codes](/img/2018-07-26-ICT 세미나 안드로이드 차세대 언어 코틀린Kotlin/4.png)

<br><br><br>


## 참고 자료

- https://thdev.tech/ [안드로이드 코틀린 컨트리뷰터 TaeHwan ]
- https://github.com/taehwandev [김태환 개발자 깃허브 ]
- http://tourspace.tistory.com/61
