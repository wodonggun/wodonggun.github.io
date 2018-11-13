---
layout: post
title: "[Android] HashKey 해시키 가져오기"
subtitle: <span class="evidence">안드로이드 스튜디오에서 해시키 쉽게 가져오기.</span>
date: 2018-11-13
author: NoonGam
category: Android
tags: Java Android
comments: true
finished: true
---

---

## 안드로이드 스튜디오




1. Oncreate 외부(클래스 메소드)에 아래의 코드 생성.
```Java
private void getAppKeyHash() {
        try {
            PackageInfo info = getPackageManager().getPackageInfo(getPackageName(), PackageManager.GET_SIGNATURES);
            for (Signature signature : info.signatures) {
                MessageDigest md;
                md = MessageDigest.getInstance("SHA");
                md.update(signature.toByteArray());
                String something = new String(Base64.encode(md.digest(), 0));
                Log.e("Hash key", something);
            }
        } catch (Exception e) {
            // TODO Auto-generated catch block
            Log.e("name not found", e.toString());
        }
    }
```

2. OnCreate 내부에 `getAppKeyHash();` 함수 호출.


3. 안드로이드 실행

<br><br><br>

## 해쉬키 결과

![img](/img/1-Everything/123.JPG);

> Logcat을 통해서 Hash key를 검색하면 위와 같이 해시키 메세지가 나옵니다.

<br><br><br>

## 참고 자료
* [[카카오 개발자 홈페이지] ](https://developers.kakao.com/docs/android/getting-started#%EA%B0%9C%EB%B0%9C%ED%99%98%EA%B2%BD-%EA%B5%AC%EC%84%B1)
