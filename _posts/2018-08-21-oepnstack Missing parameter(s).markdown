---
layout: post
title: "ERROR Missing parameter(s):
Set a username with --os-username, OS_USERNAME, or auth.username
Set an authentication URL, with --os-auth-url, OS_AUTH_URL or auth.auth_url
"
subtitle: <span class="evidence">Missing parameter(s) ERROR Solution.</span>
date: 2018-08-21
author: NoonGam
category: Study
tags: OpenStack Linux OpenSource
comments: true
finished: true
---

## Openstack - Error Missing parameter(s)

Missing parameter(s):
Set a username with --os-username, OS_USERNAME, or auth.username
Set an authentication URL, with --os-auth-url, OS_AUTH_URL or auth.auth_url
> OS 관련 해당 쉘 변수가 선언되지않고, 파라미터값이 존재하지않기때문에 위와 같은 에러를 나타낸다.


<a>위와 같이 에러가 발생하면 아래의 쉘 변수 선언과 파라미터값을 입력후 export - 코드 다시 입력후에 실행하면 정상작동</a>


```
export OS_USERNAME=admin
export OS_PASSWORD=openstack
export OS_PROJECT_NAME=admin
export OS_USER_DOMAIN_NAME=Default
export OS_PROJECT_DOMAIN_NAME=Default
export OS_AUTH_URL=http://controller:35357/v3
export OS_IDENTITY_API_VERSION=3
```
