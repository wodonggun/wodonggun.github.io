---
layout: post
title: "Ubuntu apt-get 다운로드 속도 개선 방법"
subtitle: <span class="evidence">Ubuntu apt-get 다운로드 속도 개선 방법을 알아보자.</span>
date: 2018-08-23
author: NoonGam
category: Study
tags: Network Linux
comments: true
finished: true
---



## Ubuntu apt-get 다운로드 속도 개선


![img](/img/2018-08-23-Ubuntu apt-get download 속도 개선/c.PNG)

> 기본적으로 /etc/apt/source.list에 가보면 그림과 같이 kr.archive.ubuntu.com이라는 주소에서 패키지를 받는데, Ubuntu서버는 해외에 존재하기 때문에 다운로드 속도가 현저하게 느리다. 대용량의 패키지를 받을때는 확실히 시간이 오래걸려 대부분의 시간을 다운로드하는데 사용한다.  

```
# vi /etc/apt/sources.list
```

<br><br>

![img](/img/2018-08-23-Ubuntu apt-get download 속도 개선/a.PNG)

```
%s/kr.archive.ubuntu.com/ftp.daum.net/g
```

<a>위와 같이 esc -> shift + :  -> %s/kr.archive.ubuntu.com/ftp.daum.net/g 를 입력한다.</a>


<br><br>


![img](/img/2018-08-23-Ubuntu apt-get download 속도 개선/b.PNG)
```
%s/security.ubuntu.com/ftp.daum.net/g
```

<a>위와 같이 esc -> shift + :  -> %s/security.ubuntu.com/ftp.daum.net/g 를 입력한다.</a>

<br><br>

- esc -> shift + : -> wq! -> enter

- 마지막으로 아래와같이 업데이트와 업그레이드를 통해 마무리.

```
$ sudo apt-get update
```

```
$ sudo apt-get upgrade
```



<br><br><br>



## 결과


이제 apt-get install [?] 를 다운로드받을때 매우 빠른속도로 패키지를 다운받을 수 있게 되었습니다. 체감상 apt-get install wireshark를 해보면 10~20초 걸리던 설치가 1초만에 된다.


<span class="evidence">※주의 : 네트워크를 한국에서 사용할때만 적용됩니다. 각 나라별로 대표 URL을 검색하고 변경해 주시면 됩니다. </span>
