---
layout: post
title: "AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기(2)"
subtitle: <span class="evidence">아마존 웹서비스(AWS) EC2 Ubuntu에 기본적인 데이터베이스인 MySQL과 phpMyAdmin을 설치해보자</span>
date: 2017-09-13
author: NoonGam
category: AWS
tags: EC2
comments: true
finished: true
---
## 이전 포스팅 참고하기

https://wodonggun.github.io/wodonggun.github.io/aws/AWS-EC2-Ubuntu%EC%97%90%EC%84%9C-MySQL,phpMyAdmin-%EC%84%A4%EC%B9%98%ED%95%98%EA%B8%B0(2).html

## 필요한 프로그램 설치




![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/1.png)
- ```apt-get update```
- ```apt-get install apache2 php5 mysql-server```

> apt-get update를 통해 패키지들과 버전 리스트를 업데이트를 확인한다.


<br>

<br>![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/2.png)



> 필요한 패키지 설치 apache2 php5 mysql-server

<br>![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/3.png)

> 설치 계속하려면  y 엔터

<br>![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/4.png)

> mysql에 접속할 루트 비밀번호를 입력합니다.

<br>![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/5.png)

> 비밀번호 재입력 합니다.



<br>


![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/6.png)
- ```a2enmod rewrite```

> ubuntu는 mod_rewrite가 설정되어있지 않습니다. 서버에 요청된 메세지가 정해진 규칙에 의해 URL 또는 FILE로 보냅니다.

<br>
![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/7.png)

-  ```service apache2 restart```
> 아파치를 재시작합니다.(재시작을 해야 적용이 됩니다)

<br>![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/8.png)

> 인터넷창을 통해서 IP를 입력하면 아파치 화면이 뜨면 정상적으로 설치가 완료된것 입니다.

<br>![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/9.png)

- ```vi /etc/apache2/apache2.conf```
> vi는 편집기를 실행하는 명령어 입니다. 절대경로를 통해
 /etc/apache2 폴더로 이동하고, apache2.conf를 vi편집기로 엽니다.



<br>![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/10.png)
```ruby
Include sites-enabled
Include /etc/phpmyadmin/apache2.conf
ServerName localhost
```
> 맨 아래끝에 i를 누른후(수정 모드) 코드를 입력합니다. 입력이 끝난후 esc키를 누르고 ' :wq ' 를 입력합니다.(수정내용을 덮어쓰고, 종료를 의미)
<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/11.png)

- ```vi /etc/php5/apache2/php.ini```


<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/12.png)

- esc키를 누르고 `:/default-charset` (default_charset 단어 검색하는 방법)


<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/13.png)
- ```default_charset = "UTF-8" ``` 을 입력합니다.


<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/14.png)
- 언제나 종료 할때는 esc키를 누르고 ``` :wq ``` 입력


<br>![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/15.png)

- ```vi /etc/mysql/my.cnf ```를 실행
- \[Client\]부분에 ```default-character-set = utf8 ``` 입력


<br>
![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/16.png)

 - \[mysqldump\]부분에 ```default-character-set = utf8 ``` 입력
 - \[mysql\]부분에 ```default-character-set = utf8 ``` 입력

<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/17.png)

> bind-address 앞에 #을 붙여 주석처리 또는 지워줍니다.
( 로컬(루프백 아이피) 주석을 통해 퍼블릭 접근을 가능하게 합니다. )

<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/18.png)

- \[mysqld\]부분에 아래와 같이 코드 입력

```
init_connect = 'SET collation_connection = utf8_unicode_ci'
init_connect = 'SET NAMES utf8'
character-set-server = utf8
collation-server = utf8_unicode_ci
```



<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/20.png)

> 언제나 종료할때는 esc누르고 ``` :wq! ``` 를 입력

<br>
![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/21.png)

- ```apt-get install phpmyadmin``` 입력

<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/22.png)

>  설치 계속 y 엔터

<br>
![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/23.png)

> 좀전에 설치했던 apache2를 선택합니다.

<br>
![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/24.png)
<br>
![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/25.png)
- ```service apache2 restart```

> phpmyadmin설치가 완료되면 다시 재시작 합니다.


<br>

![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/26.png)

> - ```service mysql restart```

> mysql도 재시작 합니다.
(재시작 부분에서 에러가 발생한다면 코드를 잘못 입력했거나, 설정에서 문제가 발생한걸로 다시 처음부터 천천히 확인해보세요.)

<br>
![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/27.png)

> 인터넷창에 xxx.xxx.xxx.xxx(ip주소) / phpmyadmin 을 입력하여 위와 같이 뜬다면 설치가 성공적으로 되었습니다.
설치하면서 설정했던 root 비밀번호로 로그인 합니다.

<br>
![icon](/img/2017-09-12-AWS EC2 Ubuntu에서 MySQL,phpMyAdmin 설치하기2/28.png)

<span class="evidence">AWS EC2 서버에 mysql phpmyadmin 연동이 끝났습니다!!! <span>

<br>

## puttygen 실행




<br>
<br>

     이렇게 Putty(푸티)를 통한  AWS EC2 원격 접속을 성공해 보았습니다.

<br>
<br>
<br>

## 다음 주제....

python을 통해서 간단히 데이터베이스 연결 확인 및 데이터 읽고 쓰기를 진행하겠습니다.
