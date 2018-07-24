---
layout: post
title: "미디어 쿼리? "
subtitle: <span class="evidence">미디어 쿼리란? </span>
date: 2018-07-09
author: NoonGam
category: Study
tags: Markdown Language
comments: true
finished: true
---


<!-- Study Sample  -->

## 미디어 쿼리

> 미디어 쿼리는 CSS3 모듈중 하나로, 접속하는 각각 장치에 따라 특정 CSS 스타일을 사용하도록 해주는 기능

- 해당 기기의 화면 넓이가 960 이하라면, 다른 스타일 적용하기

<style>
  body{
    background-color:gray;
  }
  @media screen and (max-width:960px)
  {
    body{
      background-color:red;
    }
  }

  @media screen and (max-width:520px)
  {
    body{
      background-color:red;
    }
  }

</style>


- 단말기의 가로,세로 모드에 따라 적용 다르게 하기

@media screen and (orientation:landscape){
  body{
    background-color:orange;
  }
}
@media screen and (orientation:portrait){
  body{
    background-color:yellow;
  }
}


- 폰트 사이즈 결정할때
예전에는 모니터 해상도를 기준으로 픽셀단위로 표시하였지만 현재는 N-screen 사용으로 유동적이지 않음.
정확하게 글자를 표시하고 싶으면 em 단위를 사용해야한다.
1em은 16px와 같음.

.header{
  font-size:1.5em;    <--- 16px * 1.5 = 25px크기임.
  font-family: "Comic Sans MS";
}
