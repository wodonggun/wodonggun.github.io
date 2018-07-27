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

## 코틀린(Kotlin) 이란 ?

- what is Kotlin?

![Codes](/img/2018-07-26-ICT 세미나 안드로이드 차세대 언어 코틀린Kotlin/k1.png)

  > Kotlin이란 ㅁㄴㅇㄻㄴㄹ



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


## 단축키

ctr alt shift k 를 누르면 자동으로 jave->kotlin 변경 됨



## var와 val의 차이
> var은 Read & Write가 가능한 변수이고, val은 Read만 가능한 변수이다.


* Java
mutable 변수
String str = "abc";

immutable
final String str = "abc";



* Kotlin은
mutable 변수
var str = "abc";

immutable
val str str = "abc";


## data class

> getter와 setter를 사용하지않고도 변수를 변경 가능하다. data class를 통해서 가능.

```php
data class hi(
      var id : Int,
      var name: String,
      var age: Int
  )

```



## 다중 상속

인터페이스와 추상클래스 생성자를 둘다 호출 가능.
자바에서는 추상클래스와 인터페이스를 동시에 상속받으면 생성자호출시에 추상클래스를 호출하는데
코틀린은 init<클래스명>.init() 으로 호출 가능






## 코틀린 문법
 mutual
-  Read/wrtie =  String v;
  final String





var name: String : ""




when (a){
  is Int -> println(a)
  is String -> println(a)
  else -> println("Nothing")


}

- 전역변수 constructor(a: String, b: String) : this(a)





@JvmStatic 를 붙여주면 마음대로 가져올 수 있다.


## 어디서든 자바에서 접근하기

@file:JvmName("LifecycleExtensionUtil")

다른 클래스파일에서 LifecycleExtensioUtil."클래스"로 해당 메소드 접근 가능





<br>
<br>
<br>

## 환경설정



## 참고 자료

- [김태환] 안드로이드 코틀린 컨트리뷰터 https://thdev.tech/
- http://tourspace.tistory.com/61



http://blog.naver.com/PostView.nhn?blogId=ouwukwfy&logNo=220248439711&parentCategoryNo=16&categoryNo=&viewDate=&isShowPopularPosts=true&from=search
