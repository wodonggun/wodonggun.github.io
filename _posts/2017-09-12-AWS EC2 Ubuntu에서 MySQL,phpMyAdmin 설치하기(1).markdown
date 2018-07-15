---
layout: post
title: "AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기(1)"
subtitle: <span class="evidence">아마존 웹서비스(AWS) EC2 Ubuntu에 기본적인 데이터베이스인 MySQL과 phpMyAdmin을 설치해보자</span>
date: 2017-09-12
author: NoonGam
category: AWS
tags: EC2 MySQL phpmyadmin linux
comments: true
finished: true
---
## 이전 AWS EC2 인스턴스 생성하기 참고하기

https://wodonggun.github.io/wodonggun.github.io/aws/AWS-EC2-Ubuntu-%EC%83%9D%EC%84%B1%ED%95%98%EA%B8%B0.html


## AWS EC2 서버에 putty를 통한 원격 접속

- putty.exe 와 puttygen.exe 다운받기 <br>
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


![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/7.png)

>  SSH -> Auth를 클릭후에 puttygen으로 생성한 pem키를 가져옵니다.


<br>
![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/8.png)

>  서버의 IP주소, SSH 포트번호 22, 즐겨찾기처럼 설정을 저장하고 불러올 수 있게 Saved Sessions를 결정합니다.

<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/9.png)

> AWS EC2 서버의 IP 주소는 위와 같이 확인할 수 있습니다.

<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/10.png)


<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/11.png)

>  login 아이디는 디폴트값으로 ubuntu로 되어있습니다.

<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치/12.png)<br>

> 위와 같은 화면이 뜨면 원격 접속 성공입니다.




<br>
<br>

     이렇게 Putty(푸티)를 통한  AWS EC2 원격 접속을 성공해 보았습니다.

<br>
<br>
<br>

## 다음 글

<span class="evidence">MySQL phpMyAdmin 설치하기(2) 바로가기<span>

https://wodonggun.github.io/wodonggun.github.io/aws/AWS-EC2-Ubuntu%EC%97%90%EC%84%9C-MySQL,phpMyAdmin-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0(2).html
