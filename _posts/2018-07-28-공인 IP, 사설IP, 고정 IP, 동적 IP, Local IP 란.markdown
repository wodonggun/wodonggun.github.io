---
layout: post
title: "공인 IP, 사설IP, 고정 IP, 동적 IP, Local IP 란?"
subtitle: <span class="evidence">공인(public), 사설(private), 고정(static), 동적(dynamic) IP에 대해서 알아보자.</span>
date: 2018-07-28
author: NoonGam
category: Study
tags: Network
comments: true
finished: true
---


## 공인 IP, 사설 IP, 고정 IP, 동적 IP, Local IP


![Codes](/img/2018-07-29-공인 IP, 사설IP, 고정 IP, 동적 IP, Local IP 란/1.jpg)


> <a>공인 IP</a>란 SK브로드밴드, Olleh KT, LG U+ 와 같은 ISP에게서 대여받은 IP를 말합니다. 이는 고정IP와 동적IP(=유동IP)로 나눌 수 있는데, 일반적으로는 기업은 고정 IP를 할당받고, 가정에서는 유동IP를 할당 받습니다.
(유동적으로 자동 IP 할당 방식 -> DHCP=Dynamic Host configuration Protocol)




> <a>사설 IP</a>란 일명 공유기를 통해 할당한 IP를 말합니다. 공유기를 통해서 DHCP사용 여부에 따라 고정IP와 동적IP로 나눌 수 있습니다.



<br>


- 기업은 IP를 고정적으로 가지고 있어야 보안이나 내부망 관리에 매우 편리하며, 가정에서는 요청하여 고정아이피를 할당 받을 수 있습니다.
- 우리가 자주쓰는 공유기에 연결하여 IP를 읽어보면 192.168.xxx.xxx라고 읽힌다. 이건 주로 가정용 공유기에 많이 쓰이는 주소이다.
기업용 공유기나 망에 접속하다보면 10.xxx.xxx.xxx가 많으며, 주로 기업에서 사용된다.
```
10.0.0.0 ~ 10.255.255.255
172.16.0.0 ~ 172.31.255.255
192.168.0.0 ~ 192.168.255.255
```
- 127.0.0.1은 Localhost IP이다. 일명 <a>루프백 아이피</a>라고도 부르며, 컴퓨터 자기자신을 가리키는 아이피이다.
- 공유기에서 아이피를 고정으로 할당하면, 아이피를 반납하기 전까지는 사용할 수 없고, 같은 아이피가 존재하면 아이피 충돌이 일어나게 된다.




<br><br><br>

## 참고 자료

- [시크릿츠님의 블로그](https://m.blog.naver.com/PostView.nhn?blogId=xcripts&logNo=70121283191&proxyReferer=https%3A%2F%2Fwww.google.co.kr%2F)
