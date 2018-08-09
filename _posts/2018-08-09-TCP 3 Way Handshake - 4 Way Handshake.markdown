---
layout: post
title: "TCP 3 Way Handshake - 4 Way Handshake"
subtitle: <span class="evidence">Session Established에 필요한 방식과 Wireshark를 통해 확인해 보자.</span>
date: 2018-08-09
author: NoonGam
category: Study
tags: Network Linux Wireshark
comments: true
finished: true
---



## 3 way handshake

![img](/img/2018-08-09-TCP 3 Way Handshake - 4 Way Handshake/1.png)

> TCP는 장치들 사이에 논리적입 접속을 성립하기 위해서 3-way handshake를 사용합니다. 어떠한 데이터를 전송하기 전에
먼저 신뢰성있는 전송을 위해 상대방 컴퓨터와 사전에 세션을 수립하는 과정을 의미합니다.

```
Client -> Server  =    SYN를 통한 서버쪽으로의 접속 요청
Server -> Client  =    SYN ACK 플래그를 통한 접속 수락
Client -> Server  =    ACK
```

<a>Syn = Synchronize sequence numbers</a>
<a>Ack = Acknowledgement</a>


<br><br><br>

## wireshark를 이용한 Session Established 확인

![img](/img/2018-08-09-TCP 3 Way Handshake - 4 Way Handshake/3.png)

> FTP통신을 통해 데이터를 전송받고 그 과정에서 데이터를 sniffing하는 모습이다.
왼쪽의 터미널 창은 wireshark에서 제공하지않는 한글 데이터를 직접 코딩하여 필요한 정보만 스니핑 하는 과정이고, 오른쪽은 wireshark를 통해 모든 패킷의 흐름을 읽어본 과정이다.

```
Client -> Server  =    SYN
Server -> Client  =   SYN ACK
Client -> Server  =    ACK
```

<br><br><br>

## 4 way handshake

![img](/img/2018-08-09-TCP 3 Way Handshake - 4 Way Handshake/2.png)

> 3-Way handshake는 TCP의 세션 수립을 위해 사용한다면, 4-Way handshake는 세션을 종료하기 위해 수행되는 절차입니다.

```

Client -> Server : TCP FIN (종료 요청)

Server -> Client : TCP ACK (요청 에크)

Server -> Client : TCP FIN (종료 완료 전송)

Server -> Client : TCP ACK (종료 완료 ACK)

```







<br><br><br>

## wirshark를 이용한 Session Released 확인


![img](/img/2018-08-09-TCP 3 Way Handshake - 4 Way Handshake/4.png)

> 위의 그림은 ACK와 FIN,ACK로 이루어져 있습니다. 4 way handshake방식이 아닌 3 way handshake 방식으로도 세션을 종료 할 수 있습니다.
 A가 (FIN,ACK)방식으로 동시에 데이터를 보내면
 B가 (FIN,ACK)방식으로 다시 A에게 보내주며,
 A는 ACK를 통해 세션 종료를 완료합니다.

```
client > Server : TCP FIN,ACK  (세션 종료 요청)

Server > client : TCP FIN,ACK  (세션 종료 및 에크 플래그 동시에 전송)

Server > Client : TCP ACK      (종료 확인 ACK)

```

<br><br><br>

## 참고 자료
* [MindNet님의 블로그] (http://mindnet.tistory.com/entry/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-22%ED%8E%B8-TCP-3-WayHandshake-4-WayHandshake)
