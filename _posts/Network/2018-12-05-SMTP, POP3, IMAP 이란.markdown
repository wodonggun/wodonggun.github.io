---
layout: post
title: " [Network] SMTP, POP3, IMAP 이란? "
subtitle: <span class="evidence"> SMTP POP3 IMAP 비교하기. </span>
date: 2018-12-05
author: NoonGam
category: Study
tags: Network Linux
comments: true
finished: true
---

---




## SMTP(Simple Mail Transfer Protocol)


> 인터넷에서 이메일을 보낼 때 사용되는 프로토콜로 메일 서버간의 송수신뿐만 아니라 메일 클라이언트에서 메일 서버로 메일을 보낼 때 사용된다.

TCP 포트 : 25번

아래 POP3, IMAP은 둘다 메일을 받아 오는 역할이고, SMTP는 메일을 보내는 역할을 한다.



## POP3(Post Office Protocol Version 3)


> 서버에 도착한 메일을 클라이언트에서 직접 내려받아 읽도록 해주는 프로토콜로 110 번 포트를 사용한다. POP3 는 구현이 용이하고, 기존의 많은 클라리언트 프로그램이 지원한다는 장점이 있으나, 메일을 확인하면 서버로부터 메일을 클라이언트로 가지고 온 후 서버에서 해당 메일을 삭제한다. 따라서 다른 곳에서 다시 메일을 확인하려면 남아 있지 않아 확인할 수 없게 되는 단점이 있다.

TCP 포트 : 110번

장점 : 구현이 쉽다. 많은 클라이언트에서 지원한다.

단점 : 서버로부터 메일을 가져온 후 삭제한다. 서버에선 더이상 메일 확인 불가



## IMAP(Internet Mail Access Protocol)


> POP3 와 마찬가지로 클라이언트 사용자가 메일 서버에 도착한 메일을 확인할 때 사용하는 프로토콜로 143 번 포트를 사용하다. POP3 와의 차이점은 메일을 확인한 후에도 서버에 해당 메일이 계속적으로 존재하여 다른 곳에서 메일 확인이 가능하다는 장점이 있으나 메일 서버의 통신 트래픽을 높이는 단점이 있다.


TCP포트 143

장점 : 메일을 가져와도 서버에 메일이 그대로 남아있다.

단점 : 서버 트래픽이 많이 쓰인다.



<br><br><br>

## 참고 자료
* http://ccm3.net/archives/24266 [The Blog of Grinbi님의 블로그]
