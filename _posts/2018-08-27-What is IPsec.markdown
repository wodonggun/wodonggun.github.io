---
layout: post
title: "IPsec 이란? - What is IPsec?"
subtitle: <span class="evidence">IPsec에 대한 간단한 소개 및 실습</span>
date: 2018-08-27
author: NoonGam
category: Study
tags: Network Linux
comments: true
finished: true
---


-----

<br><br>

## IPsec - Internet Protocol Security

> IPSec은 Internet Protocol Security의 약어로서 통신중 network layer에서의 보안을 위한 표준이다. IPSec은 인터넷 상에서 VPN(Virtual Private Network)을 구현하는데 사용될 수 있도록 IETF (Internet Engineering Task Force)에서 개발된 protocol set이다. 이는 네트워크상의 IP layer에서의 보안에 중점을 두었으며, 사설 및 공중망을 사용하는 TCP/IP 통신을 보다 안전하게 유지하기 위한 end-to-end encryption과 authentication을 제공한다.

1. 네트워크계층(IP 계층) 상에서 IP 패킷 단위로 `인증`,`암호화`,`키관리`를 하는 프로토콜

2. VPN을 구현하기 위해 만든 프로토콜(Tunnel Mode)

3. Transport계층 아래에서 구현되며, 운영체제에서 IPsec을 지원함.

4. 서로 키관리를 통해 캡슐화 및 디캡슐화를 진행

<br>

- SA (Security Association 보안연관)

<fieldset id="gpg-fieldset">
ㅇ 데이터의 안전한 전달을 위해 통신의 쌍방 간의 약속<br>
   - 암호 알고리즘, 키 교환 방법, 암호화 키 교환 주기 등에 대한 합의<br>
       이는 통신 연결 이전에 쌍방 간에 합의가 있어야 함<br><br>

   - 결국, 구체적으로 합의되어야 할 요소들의 결합을 보안연합 이라함<br>
      하나 이상의 보안서비스를 구현하기 위한 보안 속성들의 연결 집합<br>
<br>
ㅇ 특징<br>
   - 각 SA 마다 단 방향성(Unidirectional)이고, 양 방향성을 이루려면 쌍으로 구성되게 됨<br>
   - 따라서, 각 SA 마다 이를 구분하는 식별자(SPI)가 있게 됨<br>
</fieldset>


<br><br><br>


## IPsec Tunnel Mode / Transport Mode


![img](/img/2018-08-27-What is IPsec/2.png)



![img](/img/2018-08-27-What is IPsec/1.PNG)


- Tunnel Mode




- Transport Mode



<br><br><br>

## IPsec 설정 이전과 이후

- 패킷의 암호화를 확인하기 위해 패킷을 스니핑하는 방법을 선택하였습니다.

- 아스키코드 영어나 문자만 사용한다면 일반적인 wireshark를 통해 패킷을 확인할 수 있습니다.

<a>`wireshark`를 통해서는 한글형식이 지원되지 않아서 `sniffing파일`을 직접 구현하였습니다.</a>


<br><br>

![img](/img/2018-08-27-What is IPsec/ipsec1.PNG)

- 패킷 IPsec 설정 이전에 패킷 스니핑을 확인한 결과

<br><br>

![img](/img/2018-08-27-What is IPsec/ipsec3.PNG)

- IPsec start를 통한 암호화 시작.

<br><br>

![img](/img/2018-08-27-What is IPsec/ipsec2.PNG)

- IPsec start 후에는 데이터를 알아볼 수 없는 형태로 암호화하여 데이터를 전송합니다.

- 목적지에 도착하면 복호화 키에 맞춰 암호화를 해제하여 데이터를 저장합니다.

<br><br><br>

## 스니핑 과정

![img](/img/2018-08-27-What is IPsec/ipsec4.gif)

`[ 과정 ] `
1. A는 B로부터 FTP 통신을 통해 데이터를 받고 있습니다.

2. A는 tx rx가 잘 되고있는지 speedometer를 통해 확인합니다.

3. `./snif2 enp0s8`을 통해 스니핑 파일과 감시할 네트워크 인터페이스를 지정합니다.

4. `ipsec start`를 통해서 암호화를 시작합니다.

FTP , IPsec, 패킷 스니핑, wireshark 등은 따로 설치 및 설정해주어야 합니다.<br>
(여유 될때마다 조금씩 포스팅해보겠습니다!!)


<br><br><br>

## MTU maximum transmission unit

- MTU는 대부분 이더넷에 의해 결정됨.

- 헤더(header) 또는 패킷 당 지연(per-packet delay)과 같은 고정된 프로토콜 오버헤드가 있는 반면, MTU가 클수록 패킷은 한번에 많은 데이터를 전송하기 때문이다

- 느린 링크를 점유하게되면 이후 패킷들을 지연시키고, 지연 및 최소 대기시간이 증가하게 됨.

- 데이터 오류 발생시, 하나의 비트가 잘못되더라도 전체 패킷을 다 전송해야 하므로, 트래픽 증가

- 비트 에러율은 패킷이 클수록 손상되기 쉽다.

- 패킷 재전송 시간이 오래걸린다.

- 하지만 end To end 에서볼때 MTU가 클수록 긍정적인 효과가 크다.



## 정리

인증 = 상대방이 자신이 원하는 목적지가 맞는지
기밀성 = 가로채더라도 볼 수 없도록 데이터 암호화
무결성 = 내용이 변경되지않았음을 보장

 패킷 암호화 -> 인증(AH)헤더 장착 ->  새로운 IP헤더 장착 -> 중간에

`[new IP header | AH header | origin IP header | TCP/UDP header | payload ]`
 (호스트나 보안 게이트웨이에 적용)

 전송모드는 IP헤더의 일부분까지만 인증되지만
 터널모드는 새 IP헤더의 일부분부터 원본 IP헤더와 페이로드까지 인증됨.
 `(VPN이나 터널로 설정된 경로는 새로운 IP헤더를 통해 찾아가고 마지막 게이트웨이 단에서 새로운 IP헤더를 해제하고 목적지를 찾아감=public 인터넷망을 보안 터널을 통해 통과후 회사 내부망(게이트웨이)에 도착하면 원래 IP헤더를 가지고 목적지를 찾으러 감)`

 2계층에서 터널링 = PPTP L2TP
 3계층에서 터널링 = IPsec



 AH헤더는 네트워크를 통해 보낸 송신자가 누구인지를 인증하는 것이다.
 제 3자가 마치 자기가 송신한것처럼 패킷을 가로채고 전송하는것을 방지.




<br><br><br>

## 참고 자료

* https://docs.oracle.com/cd/E26925_01/html/E25873/ipsec-ov-13.html
* [ZDnet Korea 기사]( http://www.zdnet.co.kr/news/news_view.asp?artice_id=00000010052877&type=det&re=zdk)
