---
layout: post
title: "What is IPsec?"
subtitle: <span class="evidence">IPsec에 대한 간단한 소개</span>
date: 2018-01-01
author: NoonGam
category: Study
tags: Network Linux
comments: true
finished: true
---



## IPsec - Internet Protocol Security

> IPSec은 Internet Protocol Security의 약어로서 통신중 network layer에서의 보안을 위한 표준이다. IPSec은 인터넷 상에서 VPN(Virtual Private Network)을 구현하는데 사용될 수 있도록 IETF (Internet Engineering Task Force)에서 개발된 protocol set이다. 이는 네트워크상의 IP layer에서의 보안에 중점을 두었으며, 사설 및 공중망을 사용하는 TCP/IP 통신을 보다 안전하게 유지하기 위한 end-to-end encryption과 authentication을 제공한다.

1. 네트워크계층(IP 계층) 상에서 IP 패킷 단위로 `인증`,`암호화`,`키관리`를 하는 프로토콜

2. VPN을 구현하기 위해 만든 프로토콜(Tunnel Mode)

3. Transport계층 아래에서 구현되며, 운영체제에서 IPsec을 지원함.

4. 서로 키관리를 통해 캡슐화 및 디캡슐화를 진행
- SA (Security Association 보안연관)

<fieldset id="gpg-fieldset">
ㅇ 데이터의 안전한 전달을 위해 통신의 쌍방 간의 약속
   - 암호 알고리즘, 키 교환 방법, 암호화 키 교환 주기 등에 대한 합의
      . 이는 통신 연결 이전에 쌍방 간에 합의가 있어야 함

   - 결국, 구체적으로 합의되어야 할 요소들의 결합을 보안연합 이라함
      . 1 이상의 보안서비스를 구현하기 위한 보안 속성들의 연결 집합

ㅇ 특징
   - 각 SA 마다 단 방향성(Unidirectional)이고, 양 방향성을 이루려면 쌍으로 구성되게 됨
   - 따라서, 각 SA 마다 이를 구분하는 식별자(SPI)가 있게 됨
</fieldset>

## IPsec Tunnel Mode / Transport Mode

- Tunnel Mode =




- Transport Mode


![img](/img/2018-08-07-What is IPsec/1.PNG)





<br><br><br>


## MTU maximum transmission unit

- MTU는 대부분 이더넷에 의해 결정됨.

- 헤더(header) 또는 패킷 당 지연(per-packet delay)과 같은 고정된 프로토콜 오버헤드가 있는 반면, MTU가 클수록 패킷은 한번에 많은 데이터를 전송하기 때문이다

- 느린 링크를 점유하게되면 이후 패킷들을 지연시키고, 지연 및 최소 대기시간이 증가하게 됨.

- 데이터 오류 발생시, 하나의 비트가 잘못되더라도 전체 패킷을 다 전송해야 하므로, 트래픽 증가

- 비트 에러율은 패킷이 클수록 손상되기 쉽다.

- 패킷 재전송 시간이 오래걸린다.

- 하지만 end To end 에서볼때 MTU가 클수록 긍정적인 효과가 크다.






<br><br><br>

## 참고 자료

* https://docs.oracle.com/cd/E26925_01/html/E25873/ipsec-ov-13.html
*


 샘플 파일
