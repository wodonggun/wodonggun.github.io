---
layout: post
title: "openstack 이란? "
subtitle: <span class="evidence"> SDN NFV VNF 5G와 관련된 openstack? 관련된 용어들을 정리해보자.</span>
date: 2018-08-13
author: NoonGam
category: openstack
tags: OpenStack Linux OpenSource
comments: true
finished: true
---


## 클라우드 컴퓨팅

> 개인이 가진 스마트 폰, 스마트패드, 스마트 TV, 노트북,
컴퓨터와 같은 인터넷이 가능한 디바이스를 통해
클라우드라고 불리는 제 3의 공간에서 데이터를 읽고
쓰고 정보를 분석하고 처리하여, 저장하고 관리하는
컴퓨팅 시스템.

<br><br><br>

## 클라우드 서비스란 ?

> 무엇을 서비스하냐에 따라 SaaS, PaaS, IaaS 로 나눕니다.

[IaaS, PaaS, SaaS란 무엇인가?](https://wodonggun.github.io/wodonggun.github.io/study/IaaS,-PaaS,-SaaS.html)

<br><br><br>

## Floating IP?

일반적으로 외부에서 제공되는 public IP를 Fixed된 상태로 IP를 얻습니다. 일반적으로는 외부와
인터넷이 가능하지만 오픈스택을 통해 가상화로 할당받은 private IP는 외부와 통신이 불가능합니다.
floating IP는 가상 인스턴스에 IP를 부여했다가 필요에 의해서 삭제하는 IP를 지칭합니다.
하지만 이러한 floating IP를 통해 가상 인스턴스도 외부와 인터넷 통신이 가능합니다.

<br><br><br>

## 하이퍼 바이저 타입

> 하이퍼바이저는 호스트 컴퓨터 1대에서 운영체제 다수를 실행하기 위한 논리적 플랫폼을 의미합니다. 즉, VMM(Virtual Machine Monitor)라고 부릅니다.

- Native(물리적 분할 개념) = 운영체제보다 위에 하이퍼바이저개념이 상주하여 여러개의 OS를 프로그램 다루듯이 제어함

- Hosted(가상머신 개념) = 운영체제 아래에 하이퍼바이저를 두고 하이퍼바이저내부에 여러개의 OS를 구동 시킴


가상머신은 하이퍼바이저위에 별도의 운영체제와 함께 동작
컨테이너는 공통된 운영체제를 기반으로 독립적으로 응용프로그램을 실행합니다.



## SDN - Software Defined Networking

네트워크 제어기능이 물리적 네트워크와 분리되도록 프로그래밍한 네트워크 구조

1. 네트워크 제어 기능을 데이터 전달기능과 분리
2. 네트워크 제어 기능과 실행환경을 분리하여 성능이 낮은 하드웨어 포트에는 더이상 할당 안함.


<br><br><br>

## 오픈스택이란 ?

> 초기 RackSpace 와 NASA가 합작으로 개발




## 가상 서버를 생성하는 Nova

> OpenStack에서 Nova는 Compute Service의 핵심이며, 메세지 큐,
노바는 IaaS(Infrastructure As A Service)를 제공합니다.

1. Nova는 대시보드나 콘솔을 통해 Nova-api를 호출합니다.
2. Nova-api는 메세지큐를 통해 nova-compute에 인스턴스 생성을 명령<br>
(직접 하이퍼바이저에게 명령 불가능)
3. nova-compute는 하이퍼바이저 라이브러리를 통해 하이퍼바이저에게 인스턴스 명렁 전달
4. 하이퍼바이저 인스턴스 생성
5. 인스턴스에 nova-console을 통해 사용자가 접근 가능


## <a>¶ controller<a>

컨트롤러
컨트롤러 노드는 ID 서비스, 이미지 서비스, Compute의 관리 부분, Networking의 관리 부분, 다양한 Networking 에이전트 및 Dashboard를 실행합니다. SQL 데이터베이스, 메시지 대기열 및 NTP (Network Time Protocol)와 같은 지원 서비스도 포함됩니다.

필요에 따라 컨트롤러 노드는 블록 저장소, 개체 저장소, 오케스트레이션 및 원격 측정 서비스의 일부를 실행합니다.

컨트롤러 노드에는 최소 두 개의 네트워크 인터페이스가 필요합니다.


## <a>¶ compute<a>





## 오브젝트 스토리지 Swift



## 정리

1. 네트워크 슬라이싱
- NFV를 서로 호환에 맞춰 나눔
- NFV의 다양한 기능 중에

2. ㅁㄴㅇㄻㄴㅇㄹ
- ㅁㄴㅇㄹ
- ㅁㄴㅇㄹ

## 오픈스택
> 퀀텀을 시도하였으나, 계속 문제가 발생하여 뉴턴으로 결정



오픈스택은 controller와 compute의 2개로 나누어져 있다고 생각하면 된다.
- controller : 네트워크,DB(Keystone),스토리지 제공
- compute : 계산작업, 자원할당, VM 할당


keystone = 모든 프로젝트 인증 관리
Cinder = 스토리지=block storage(aws EBS Elastic Block store로 생각해도 됨.)
swift = 오프젝트 스토리지로 REST API를 통해 파일 관리(aws 버킷이랑 비)
nova = 서버 가상화 컴퓨팅
horizon = 대쉬보드
glance = nova에서 서버를 가상화할 때 필요한 OS 이미지 관리
뉴트론 : 네트워크,리눅스 브릿지, 로드밸런싱? SDN 지원




<br><br><br>

## 네트워크

- Provider Network (그냥 일반적인 네트워크 서비스)
기본으로 라우터나 장비를 그대로 받아서 씀.

프로바이더 브릿지로 인터페이스를 만들고 연결


- self-service Network ( 스스로 모든 네트워크를 다 관리)
라우터 동작 ,DHCP,포트포워딩 등 소프트웨어로 직접 구성하고 관리

프로바이더 브릿지로 인터페이스를 연결한걸 쓰면서 + 셀프 서비스브릿지로 내부 VLAN터널을 만들고 외부와 통신도 가능하게
