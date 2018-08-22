---
layout: post
title: "오픈스택 설치"
subtitle: <span class="evidence"> SDN NFV VNF 5G와 관련된 openstack?</span>
date: 2018-08-13
author: NoonGam
category: openstack
tags: OpenStack Linux OpenSource
comments: true
finished: true
---

## 가상머신

램4기가
하드 50기가
서버버전으로 설치


ubuntu 16.04 server 버전

1. English -> english -> location= republic of korea -> US키보드 -> detect = NO -> US ->

Encrypt = yes

hdd -> entired disk -> 선택

write change ? = yes

install security update auto

proxy = continue


software selection = standard system utility , virtual machine host , openssh server 선택

gurb = yes

install = continue  


## mysql 비밀번호 변경

mysql -u root -p

use mysql;

update user set password=password('비번') where user='root';

flush privileges;
