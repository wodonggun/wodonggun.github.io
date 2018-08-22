---
layout: post
title: "Robots.txt와 meta name="robots" 차이"
subtitle: <span class="evidence">크롤링과 인덱싱의 차이를 이해하고 효율적으로 웹을 관리하자.</span>
date: 2018-01-01
author: NoonGam
category: Study
tags: Network Linux
comments: true
finished: true
---


## 검색엔진의 크롤링과 인덱싱의 차이

<a>크롤링 제어는 robots.txt</a><br>
<a>인덱싱 제어는 < meta name="robots" content="noindex"> </a>

> 검색엔진이 검색 키워드에 대한 검색결과를 사용자한테 제공하기 위해서는 크롤러가 끊임없이 온라인 상의 문서를 수집해야하고, 크롤러가 수집한 문서를 인덱서가 잘 정리해서 인덱스 서버에 색인해 둬야 합니다.
많은 분들이 헷갈려 하는 부분인데 크롤러나 인덱서는 서로 하는일이 약간 틀립니다.
말그대로 크롤러는 단순히 사이트와 사이트 사이의 링크를 타고다니며 문서를 수집하는 역할만 하며, 인덱서는 수집된 문서를 검색엔진이 사용자에게 결과물을 좀더 빠르고 쉽게 제공할수 있도록 색인 또는 인덱스하는 역할을 합니다.<br><br>
마찬가지로 크롤러를 제어하는 방법과 인덱싱을 제어하는 방법이 다릅니다.
크롤링을 제어하려면 사이트의 루트 디렉토리에 robots.txt 파일을 사용해서 제어해야 하고,
인덱싱을 제어하려면 각각의 페이지 내에 < meta name="robots" content="noindex,nofollow"> 같은 메타 로봇 태그를 사용해서 제어해야 합니다.

##

< meta name="robots" content="index" />
< meta name="robots" content="noindex" />

< meta name="robots" content="index,follow" />
< meta name="robots" content="index,nofollow" />
< meta name="robots" content="noindex,follow" />
< meta name="robots" content="noindex,nofollow" />





<br><br><br>

## 마무리

크롤링과 인덱싱의 역할, 그리고 robots.txt 파일과 meta robots 태그의 사용방법을 잘 알아야 하며, 인덱스의 차단하는 역할은 ```< meta name="robots" content="noindex">```가 ```robots.txt``` 보다 우위에 있다는걸 숙지해야 합니다.





<br><br><br>

## 예시







<br><br><br>

## 참고 자료
*
*
*
