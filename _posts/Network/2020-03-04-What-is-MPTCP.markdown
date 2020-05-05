---
layout: post
title: "[네트워크] MPTCP(Multipath TCP)란? - What is MPTCP? "
subtitle: <span class="evidence">MPTCP에 대해서 알아보고 테스트배드를 구축해보자.</span>
date: 2020-03-04
author: NoonGam
category: Network
tags: Network
comments: true
finished: true
---

<br><br>
## what is MPTCP? ?


- MPTCP는 `Multipath TCP`의 약어

- 기존의 TCP Stream을 여러개 묶어서 하나의 Applicaton 또는 Host에서 데이타를 주고 받을수 있음

- MPTCP (Multi Path TCP)는 IETF에 의해 2013년 표준화된 기술로 TCP 프로토콜을 확장하여 단말과 TCP 서버간에 다수의 TCP 경로를 구성하고 다수의 경로로 동시에 데이터를 송수신하는 방법

- MPTCP는 TCP/UDP와 같이 4계층(Transport Layer) 프로토콜임
<br><br>  


## 간략한 설명

- `스마트폰 경우` : Wifi와 모바일데이터 연결을 동시에 할 수 없다.

- `PC, 노트북 경우` : Wifi, 유선케이블 연결을 동시에 할 수 없다.  

> 하지만 MPTCP를 사용한다면 2개 이상의 인터넷을 연결해서 사용할 수 있다.  
두개 이상의 인터넷을 사용하기 때문에 한쪽이 끊겨도 다른 쪽에서도 계속 다운 받을 수 있다.

> 다운로드 진행시에 2개 이상의 인터넷을 사용하여 병렬처리로 다운받을 수 있다.


<br><br>
## 특징

![img](/img/5-Network/2018-07-20-What-is-MPTCP/1.png)

- MPTCP는 호스트간 여러경로를 두어, 각각의 경로를 통해 데이타를 주고받을수 있는 장점이 있음

- 중간에 혼잡(Congestion)이 발생하거나 연결이 끊어지더라도 연속적으로 데이타를 주고 받을 수 있음

- 다중 경로 TCP는 네트워크 전반적인 트래픽 엔지니어링 효과를 얻을 수 있는 장점

- VoIP, IPTV, 게임 등과 같은 요구가 많은 서비스에게 신뢰성(reliability)을 제공하기에 적합

<a> <b title="Streaming Control Transmission Protocol 하단 참조">SCTP</b>로 구현하려면 TCP, UDP로 설정된 모든 기기들의 프로토콜을 SCTP로 변경해야 하는 단점이 있다.
하지만 MPTCP는 현재 사용되고있는 TCP구조를 그대로 사용하면서 설정만 해주면 사용할 수 있다.  
</a>

<br><br>
## 응용 기술

![img](/img/5-Network/2018-07-20-What-is-MPTCP/2.jpg)

- IP기반의 LTE망에서 혼잡에 의한 트래픽손실 방지를 위해 사용됨

- LTE 와 Wibro, WiFi 네트워크와 연동시 응용됨(LTE와 WLAN과 같이 이종망을 다중 경로로 구성하는 경우에는 WLAN과 LTE간의 Carrier Aggregation 효과를 얻을 수 있는 구조)



<br><br>
## 현재 MPTCP 상용화 사례




- 삼성의 Download Booster 기술 (추정) - MPTCP를 이용한 빠른 속도 제공

- 애플(ios)의 플로우 기술 (추정)  - 삼성과 다르게 MPTCP를 활용한 끊김없는 연결상태 보장.

- 응용계층 기반의 Proxy를 이용한 기술 (추정) - KT,SKT 등 프록시서버를 통한 MPTCP 환경 제공.

- IETF 표준상의 MPTCP (Multi-Path TCP org)  

<br><br>

## MPTCP 테스트베드

<fieldset id="gpg-fieldset"> <br>
 1. VM virtualBoX로 두개의 가상머신을 호스트로 연결하고, 라우팅 설정.  
 2. ubuntu 16.04버전에서 테스트  
 3. speedometer를 통한 속도 그래프 시각화  
 4. 자체 대역폭 계산 프로그램을 통해 TX,RX 측정  
 5. iperf를 통해 지속적인 테스트 진행  
</fieldset>

- Single_path = TCP 통신 속도 및 대역폭 테스트베드

![img](/img/5-Network/2018-07-20-What-is-MPTCP/single_path.gif)

> single_path를 통한 데이터 전송 속도 및 대역폭 측정.

<br><br>

- Multi_path = MPTCP 통신 속도 및 대역폭 테스트베드

![img](/img/5-Network/2018-07-20-What-is-MPTCP/Multi_path.gif)

> 미리 설정해놓은 쉘스크립트 MPTCP_ON을 실행후 up,down을 통해 해당 인터페이스를 제거하였을떄, 전송 속도 및 대역폭 시각화



<br><br>


## 연관 지식

SCTP(Streaming Control Transmission Protocol)

- TCP와 같은 연결지향적 프로토콜
- HTTP를 통한 IP계층의 스트리밍 전송 프로토콜
- 하나의 경로가 fail이 되도, 다중경로 지원을 통한 지속적인 데이터 전송.
- SCTP세션간 서로 여러 경로를 가질 수 있어서 path fail 발생하더라도 idle(미리 결정된) 다른경로를 통해서 데이터 전송 가능.


<br><br>
## 참고 자료

- [지금이순간 Blog](http://ensxoddl.tistory.com/263)

- [넷매니아즈 자료](https://www.netmanias.com/ko/post/blog/6719/carrier-aggregation-lte-wi-fi/integration-of-lte-and-wi-fi-networks-2-non-3gpp-based)
