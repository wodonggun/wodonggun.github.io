---
layout: post
title: "VirtualBoX 우분투 16.04 설치하기"
subtitle: <span class="evidence">가상머신에 Ubuntu 우분투 설치하기.</span>
date: 2017-09-06
author: NoonGam
category: Linux
tags: Linux
comments: true
finished: true
---


이전에 포스팅에서 [VirtualBox 설치하기](https://wodonggun.github.io/wodonggun.github.io/linux/VirtualBox-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0.html)
를 통해서 기본 세팅을 하였습니다.



## Ubuntu ISO 다운로드 받기

윈도우를 설치하려면 윈도우 CD나 USB가 있어야 하듯이,
우분투를 설치하려면 우분투 ISO파일이 있어야 합니다.
<span class="evidence">우분투 16.04버전을 사용하였으며,

https://www.ubuntu.com/download

 일반적으로 우분투 공식홈페이지에서 다운받으면 해외사이트라서 1~2시간이 넘게 소요됩니다.
그래서 우리는 더 빠른방법으로 다운로드 받습니다.
한국서버에 있는 카카오를 통해서 ubuntu 16.04 LTS를 다운받습니다.<br><br>
[ubuntu 초고속 다운로드](http://mirror.kakao.com/ubuntu-releases/)


## VirtualBox 우분투 16.04 LTS 설치

![icon](/img/2017-09-06-VirtualBox 우분투 설치/0.png)

> 이전에 생성한 ubuntu_test를 클릭하고 시작(T)를 누릅니다.

<br>

![icon](/img/2017-09-06-VirtualBox 우분투 설치/1.png)

> 폴더 표시를 클릭합니다.

<br>

![icon](/img/2017-09-06-VirtualBox 우분투 설치/2.png)

> 위에서 다운로드받은 <a>ubuntu-16.04.4-desktop-amd64.iso</a> 우분투 파일을 선택합니다.

<br>

![icon](/img/2017-09-06-VirtualBox 우분투 설치/3.png)


<br>

![icon](/img/2017-09-06-VirtualBox 우분투 설치/4.png)

> 여기서 한국어를 선택할건지 영어를 선택할건지 결정합니다. 한국어가 편하지만
나중에 능숙해지면 영어 버전을 추천합니다. 나중에 환결설정이나 언어 문제 등 다양한 문제가 생길 수 있습니다. (현재는 한국어 선택)

<br>

![icon](/img/2017-09-06-VirtualBox 우분투 설치/5.png)

> 한국어 키보드를 선택하고, 한국어는 일반적인 키보드 방식을 말하며, 한국어-한국어(101/104 호환)는 노트북 키보드에 대한 지원을 의미합니다.
<br>

![icon](/img/2017-09-06-VirtualBox 우분투 설치/6.png)

> 기본적으로 <a>일반설치</a>를 기본으로, 운영체제를 설치하면서 다른 업데이트도
동시에 진행하도록 <a>ubuntu 설치 중 업데이트</a>를 체크합니다. 다른 하드웨어 장치에 별다른 설치없이 편하게 사용할 수 있도록 모두 <a>그래픽 등 소프트웨어 설치를 체크</a>.

<br>

![icon](/img/2017-09-06-VirtualBox 우분투 설치/7.png)

<br>

![icon](/img/2017-09-06-VirtualBox 우분투 설치/8.png)

<br>

![icon](/img/2017-09-06-VirtualBox 우분투 설치/9.png)

> 이름과 암호를 결정합니다. 잃어버리지않도록 꼭 메모하거나 기억하세요.

<br>


![icon](/img/2017-09-06-VirtualBox 우분투 설치/10.png)

![icon](/img/2017-09-06-VirtualBox 우분투 설치/11.png)

> 설치가 완료되면 재부팅을 합니다.

![icon](/img/2017-09-06-VirtualBox 우분투 설치/12.png)

> 재부팅하면서 부팅중에 이러한 화면이 뜨면 Enter키를 입력합니다.

![icon](/img/2017-09-06-VirtualBox 우분투 설치/13.png)

> 아까 생성한 user를 선택합니다.

![icon](/img/2017-09-06-VirtualBox 우분투 설치/14.png)

> 패스워드를 입력합니다.

![icon](/img/2017-09-06-VirtualBox 우분투 설치/15.png)

> 이런 화면이 뜬다면 정상적으로 Ubuntu 설치가 완료되었습니다.


<br>

## Ubuntu root 비밀번호 설정

![icon](/img/2017-09-06-VirtualBox 우분투 설치/16.png)

- ```1번을 클릭한 후, 2번을 클릭합니다.```
- ```또는 ctrl+alt+t 단축키를 통해 터미널창을 엽니다.```

<br>

![icon](/img/2017-09-06-VirtualBox 우분투 설치/17.png)

- ```su 를 입력합니다.```
- ```ubuntu 부팅시에 user로 로그인했던 비밀번호를 입력합니다.```
- ```root 계정의 새로운 비밀번호를 입력합니다. ```
- ```root 계정의 새로운 비밀번호를 다시 한번 더 입력합니다. ```

![icon](/img/2017-09-06-VirtualBox 우분투 설치/18.png)

> su 명령어 입력을 비밀번호를 입력하고, 그림과 같이 최상위 관리자 root로 권한이 변경되었습니다.







<br>
<br>

## 다음 포스팅...

<br>
<br>
