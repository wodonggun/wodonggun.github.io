---
layout: post
title: "Robots.txt와 meta name= robots 차이"
subtitle: <span class="evidence">크롤링과 인덱싱의 차이를 이해하고 효율적으로 웹을 관리하자.</span>
date: 2018-08-23
author: NoonGam
category: HTML
tags: Jekyll
comments: true
finished: true
---


## 검색엔진의 크롤링과 인덱싱의 차이

- <a>크롤링 제어는 robots.txt</a><br>

- <a>인덱싱 제어는 < meta name="robots" content="noindex"> </a>
<br>

> 검색엔진이 검색 키워드에 대한 검색결과를 사용자한테 제공하기 위해서는 크롤러가 끊임없이 온라인 상의 문서를 수집해야하고, 크롤러가 수집한 문서를 인덱서가 잘 정리해서 인덱스 서버에 색인해 둬야 합니다.
많은 분들이 헷갈려 하는 부분인데 크롤러나 인덱서는 서로 하는일이 약간 틀립니다.
말그대로 크롤러는 단순히 사이트와 사이트 사이의 링크를 타고다니며 문서를 수집하는 역할만 하며, 인덱서는 수집된 문서를 검색엔진이 사용자에게 결과물을 좀더 빠르고 쉽게 제공할수 있도록 색인 또는 인덱스하는 역할을 합니다.<br><br>
마찬가지로 크롤러를 제어하는 방법과 인덱싱을 제어하는 방법이 다릅니다.
크롤링을 제어하려면 사이트의 루트 디렉토리에 robots.txt 파일을 사용해서 제어해야 하고,
인덱싱을 제어하려면 각각의 페이지 내에 < meta name="robots" content="noindex,nofollow"> 같은 메타 로봇 태그를 사용해서 제어해야 합니다.

<br><br><br>

## robots란?

> robots는 구글이나,네이버,다음 등 다양한 검색엔진에서 검색 정보를 수집하는 검색 로봇을 가리킵니다. 이러한

1. robots 관련 데이터는 헤더 또는 루트 경로에 위치해야 합니다.

2. robots 관련 내용은 [로봇 배제 표준 프로토콜[링크]](https://ko.wikipedia.org/wiki/%EB%A1%9C%EB%B4%87_%EB%B0%B0%EC%A0%9C_%ED%91%9C%EC%A4%80)을 준수해야 합니다.



<br><br><br>


## robots.txt 구성

![img](/img/2018-08-23-robots meta robots/1.PNG)

<br>

- 모든 로봇에게 문서 접근을 허락
```
User-agent: *
Allow: /
```

- 모든 로봇에게 문서 접근을 차단
```
User-agent: *
Disallow: /
```

- 네이버 로봇 접근 제한
```
User-agent: Yeti
Disallow: /
```

- 구글 로봇 접근 제한
```
User-agent: googlebot
Disallow: /
```


- 다음 로봇 접근 허용
```
User-agent: Daumoa
Allow: /
```

<br><br>

이러한 방법 말고도 다양한 처리가 가능합니다.
[링크](https://ko.wikipedia.org/wiki/%EB%A1%9C%EB%B4%87_%EB%B0%B0%EC%A0%9C_%ED%91%9C%EC%A4%80)


<br><br><br>

## robots 태그 구성


- HTML meta 태그를 이용하여 로봇을 제어할 수 있다.<br>


![img](/img/2018-08-23-robots meta robots/2.PNG)
> head부분에 robots 관련을 meta태그를 통해 설정이 가능합니다.

<br><br>

```html
<meta name="robots" content="Noindex,Nofollow" />
```
```html
<meta name="robots" content="index" />
```
```html
<meta name="robots" content="noindex" />
```
```html
<meta name="robots" content="index,follow" />
```
```html
<meta name="robots" content="index,nofollow" />
```
```html
<meta name="robots" content="noindex,follow" />
```
```html
<meta name="robots" content="noindex,nofollow" />
```




<br><br><br>

## 마무리

크롤링과 인덱싱의 역할, 그리고 robots.txt 파일과 meta robots 태그의 사용방법을 잘 알아야 하며, 인덱스의 차단하는 역할은 ```< meta name="robots" content="noindex">```가 ```robots.txt``` 보다 우위에 있다는걸 숙지해야 합니다.






<br><br><br>

## 참고 자료
* [Dothome 웹호스팅 참고]( http://blog.naver.com/PostView.nhn?blogId=anysecure3&logNo=221118269608&beginTime=0&jumpingVid=&from=search&redirect=Log&widgetTypeCall=true&directAccess=false)
