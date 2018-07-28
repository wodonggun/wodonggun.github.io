---
layout: post
title: "서울대학교 SKtechx ICT Kotlin 세미나"
subtitle: <span class="evidence">안드로이드 스튜디오에서 개발하면서 지금까지 언어는 자바로 사용되었다. </span>
date: 2018-07-09
author: NoonGam
category: Android
tags: Kotlin Language
comments: true
finished: true
---

## 2018 ICT 코틀린 세미나

> 연구 과제에 안드로이드 앱의 효용 가능성과 개발 언어, 현황 등 파악하기 위해 코틀린 관련 세미나에 참가하게 되었습니다. 


- what is Kotlin?

![Codes](/img/2018-07-26-ICT 세미나 안드로이드 코틀린Kotlin 출장/1.PNG)

  > Kotlin is a statically typed programming language that runs on the Java virtual machine and also can be compield to JavaScript source code or use the LLVM compieler infrastructure.




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


## 안드로이드 코틀린 개발 및 적용 중인 회사들


![Codes](/img/2018-07-26-ICT 세미나 안드로이드 코틀린Kotlin 출장/1.PNG)

<br><br><br>


## 참고 자료

- https://thdev.tech/ [김태환 개발자]
- http://tourspace.tistory.com/61



http://blog.naver.com/PostView.nhn?blogId=ouwukwfy&logNo=220248439711&parentCategoryNo=16&categoryNo=&viewDate=&isShowPopularPosts=true&from=search
