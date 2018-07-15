---
layout: post
title: "AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기"
subtitle: <span class="evidence">아마존 웹서비스(AWS) EC2 Ubuntu에 기본적인 데이터베이스인 MySQL과 phpMyAdmin을 설치해보자</span>
date: 2017-09-12
author: NoonGam
category: AWS
tags: EC2
comments: true
finished: true
---
## 이전 AWS EC2 인스턴스 생성하기 참고하기

https://wodonggun.github.io/wodonggun.github.io/aws/AWS-EC2-%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0.html

## AWS EC2 서버에 putty를 통한 원격 접속

- putty.exe 와 puttygen.exe 다운받기
[putty 다운로드](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)


![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/1.png)

> 자신의 운영체제와 맞는 버전 putty와 puttygen을 다운받습니다.  

<br>

## puttygen 실행

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/2.png)

> Puttygen을 실행하고 Load를 클릭합니다.

<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/3.png)
> AWS EC2 인스턴스를 생성하면서 중요하다고 말한 EC2_Test_Key1를 엽니다.

<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/4.png)
> Key -> SSH-2 RSA key로 잘 설정되어있는지 확인

<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/5.png)
> Save Private Key를 선택

<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/6.png)
> putty로 접속할 ppk 이름과 저장할 경로를 선택합니다.

<br>


## putty 실행


![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/8.png)

>  

<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/9.png)
<br>
![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/7.png)<br>
![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/10.png)
<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/11.png)<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/12.png)<br>






<br>
<br>

     이렇게 AWS EC2 접속을 성공해 보았습니다. 하이

<br>
<br>
<br>

## 마무리

[우비 가상서버 홈페이지 링크](https://woobi.co.kr "저렴한 가상 서버"){: target-"_blank"}
