---
layout: post
title: "Git Github 사용 방법"
subtitle: <span class="evidence">Git Bash를 통해 Git을 사용해보자. </span>
date: 2018-08-12
author: NoonGam
category: Git
tags: Git Github
comments: true
finished: true
---



## Git 이란?

![img](/img/2018-08-12-Git Github 사용 방법/0.png)

> Git이란 History 관리하는 도구로, History 관리를 통해 개발되어온 과정 역사를 볼 수 있고, 특정시점으로 복구가 가능합니다.
(개발 과정, 소스파일 등을 관리하는 도구)

<span>GUI(Graphic User Interface)</span>대신 CLI(Command Line Interface)를 통해 명령창 환경에 익숙해지자.(기본 유닉스,리눅스 명령어)




<br><br><br>

## 깃 설치

- 깃 다운로드 후 설치(자신의 환경에 맞는 버전 선택=windows)
https://git-scm.com/downloads

- 깃 회원가입
https://github.com/

- 아톰 편집기 다운로드
https://atom.io/






<br><br><br>

## Git 명령어

- ```$git add (파일명)```
커밋할 목록에 자신의 파일이나 폴더 추가

- ```$git commit```
히스토리의 한단위

- ```$push```
github에 밀어넣기

- ```$push --force```
github에 강제로 밀어넣기



- ```$git push origin master --force```
github에 master 브랜치에 강제로 push

- ```$git log```
commit 제출 내용 확인

- ```$git status```
현재 git 상태 확인

- ```$pwd```
현재 자신의 폴더 경로 보기

- ```#git reset HEAD~1```
가장 최근에 제출한 commit 제거





<br><br><br>

## 깃 제출 순서


1. ```$git init```  - 깃 초기화 설정

2. ```$git add (파일,폴더명)```  -  폴더명 대신에 .(점) 사용시 현재위치 모든 폴더 add

3. ```$git commit -m "남길 메세지"``` - commit log에 남길 메세지 입력 <br>(git 협력에서는 이 메세지를 통해서 복구 시점을 만들 수 있고, 문제점 발생 위치를 파악할 수 있기 때문에 대규모 프로젝트에서는 작성 규칙을 정하고 자세히 적음)

4. ```$git remote add origin <repository URL>``` - 해당 URL 연결

5. ```$git push origin master / git push origin master --force``` - history정보 push / 강제 push

<br><br><br>


## Github에 폴더 올리기

1. 상단에서 Git을 설치 안하신분은 설치해 주세요.

   [Git 다운로드 바로가기](https://git-scm.com/downloads)


![img](/img/2018-08-12-Git Github 사용 방법/1.png)

> 원하는 폴더 위치에서 우측마우스 -> Git Bash 를 실행합니다. 또는 Git bash를 실행하고 cd(디렉토리 이동) 명령어를 통해서 원하는 디렉토리로 이동합니다.  

![img](/img/2018-08-12-Git Github 사용 방법/2.png)

- ```$git init```

> 해당 폴더에 git 관련 초기화 설정을 합니다.

<br><br>

![img](/img/2018-08-12-Git Github 사용 방법/3.png)

- ```git add .```
- ```git commit -m "commit 로그에 남길 메세지"```

<br><br>

![img](/img/2018-08-12-Git Github 사용 방법/4.png)

- ```Repositories -> New 클릭```

<br><br>

![img](/img/2018-08-12-Git Github 사용 방법/5.png)

- 원하는 Repository name을 적고, Description, Public, MIT License를 설정합니다.
- 모든 설정이 완료된 후에, Create Repository를 클릭.

<br><br>

![img](/img/2018-08-12-Git Github 사용 방법/6.png)

- 해당 Repository에서 ```Clone or download```를 클릭하여, HTTPS 주소를 복사를 누릅니다.

<br><br>

![img](/img/2018-08-12-Git Github 사용 방법/7.png)

- ```git remote add origin "복사했던 Clone 주소"```

<br><br>

![img](/img/2018-08-12-Git Github 사용 방법/8.png)

- ```git push origin master```

<br><br>

![img](/img/2018-08-12-Git Github 사용 방법/9.png)

> 기본적으로는 git push origin master로 데이터를 push할 수 있지만 local저장소에서는 권한이 없기때문에 불가능합니다.

<br><br>

![img](/img/2018-08-12-Git Github 사용 방법/10.png)

- ```git push origin master --force``` 를 통해 강압적으로 무조건 push를 할 수 있게 명령합니다.


<br><br>

![img](/img/2018-08-12-Git Github 사용 방법/12.jpg)

- 해당 Repository에 올릴려면 권한이 있어야하기 때문에 인증 절차가 진행됩니다.
- Github 아이디와 비밀번호를 입력하고 로그인 합니다.

<br><br>

![img](/img/2018-08-12-Git Github 사용 방법/11.png)

- Github에 업로드를 진행합니다.

<br><br>

![img](/img/2018-08-12-Git Github 사용 방법/13.png)

- 이제 자신의 Repository에 들어가면 업로드된 파일을 볼 수 있습니다.


<br><br><br>

## pull request는 다음에...

> 다른 사람의 프로젝트에 내가 만든 commit을 제출한다.

1. 상대방의 프로젝트를 fork 뜬다
2. 내 계정에서 관리되는 프로젝트를 새롭게 만듬
3. 새로운 commit 내용들을 pull-request 제출 할 수 있다.

<br><br><br>

## 참고 자료
* https://github.com/Taeung/git-training
