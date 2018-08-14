---
layout: post
title: "VM virtualBoX putty 원격 접속 하기."
subtitle: <span class="evidence">Putty를 통해 VM에 원격으로 접속해보자.</span>
date: 2017-08-14
author: NoonGam
category: Linux
tags: VirtualBoX Linux
comments: true
finished: true
---



## putty 설치

[putty 설치 바로가기](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)

링크를 타고 들어가 ```putty.exe```를 다운받습니다.

<br><br>

![img](/img/2017-08-14-VM VirtualBoX putty 원격 접속하기/13.png)

(자신의 윈도우 버전이 64bit인지 32bit인지 윈도우 검색창에 ```dxdiag``` 입력 후 실행)

<br><br><br>

## 접속 조건

1. openSSH-server 설치 ```$ sudo apt-get install openssh-server```

2. 내부 Host 전용 어댑터 설정

![img](/img/2017-08-14-VM VirtualBoX putty 원격 접속하기/11.png)

<br><br>

3. 네트워크 인터페이스 설정 ```$vi /etc/network/interfaces```

![img](/img/2017-08-14-VM VirtualBoX putty 원격 접속하기/10.PNG)

```linux
auto enp0s8
iface enp0s8 inet static
 address 192.168.56.101
 netmask 255.255.255.0
```

<br><br>

4. host 등록
- ```$vi /etc/hosts```
- 아까 설정했던 호스트 네트워크 설정 ```192.168.56.101 ubuntu``` 추가

![img](/img/2017-08-14-VM VirtualBoX putty 원격 접속하기/12.png)


<br><br>

5. 인터페이스 설정 바뀌었으면 다시 시작을 합니다. 또는 reboot
 - ```ifconfig enp0s8 up```
 - ```ifconfig enp0s8 down```
 - ```sudo reboot```



## putty 접속

![img](/img/2017-08-14-VM VirtualBoX putty 원격 접속하기/1.png)

> network interface에서 설정했던 IP를 입력합니다.
- ```192.168.56.101```

<br><br>

![img](/img/2017-08-14-VM VirtualBoX putty 원격 접속하기/2.png)

- hostname(=user)와 password를 입력합니다.

<br><br>

![img](/img/2017-08-14-VM VirtualBoX putty 원격 접속하기/3.png)

- 이렇게 putty를 통해 VM virtualBoX에 접속을 성공하였습니다.  

<br><br>


<br><br><br>

## 참고 자료
* [안성논수저님의 블로그](https://blog.naver.com/PostView.nhn?blogId=mlnkdd&logNo=221320208914&parentCategoryNo=&categoryNo=7&viewDate=&isShowPopularPosts=false&from=postList)
* [AWS EC2 Ubuntu에서 Putty 접속](https://wodonggun.github.io/wodonggun.github.io/aws/AWS-EC2-Ubuntu%EC%97%90%EC%84%9C-MySQL,phpMyAdmin-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0(1))
