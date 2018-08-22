---
layout: post
title: "Jekyll Blog에 Google Analytics 등록하기"
subtitle: <span class="evidence"> -------- </span>
date: 2018-01-01
author: NoonGam
category: Study
tags: Network Linux
comments: true
finished: true
---



##

1. [Google Analytics 바로가기](https://analytics.google.com/analytics/web)




 ![img](/img/2018-08-22-Jekyll Google Analytics 등록/1.png)

 > 위의 링크를 타고가서 가입하고 난 후에 새 계정을 생성합니다.

 <br><br>

 ![img](/img/2018-08-22-Jekyll Google Analytics 등록/2.png)

 > 위와 같이 설정을 하고 추적 ID를 가져옵니다.  

 <br><br>

 ![img](/img/2018-08-22-Jekyll Google Analytics 등록/3.png)

 > 추적 ID를 알아낼 수 있는 방법은 여러가지 입니다.

 <br><br>

 ![img](/img/2018-08-22-Jekyll Google Analytics 등록/4.png)

 > Google Analytics의 추적 ID는 UA-xxxxxxxxx-x로 시작합니다.
 고유의 ID이기 때문에 잘 기억합니다.


 <br><br>

 ![img](/img/2018-08-22-Jekyll Google Analytics 등록/5.png)

> Jekyll 프로젝트에 _config.yml이 있을때는 google-analytics에 자신의 추적 ID를 그림과 같이 입력합니다.

 <br><br>

 ![img](/img/2018-08-22-Jekyll Google Analytics 등록/6.png)

  > 위와 같이 _config.yml이 없거나 google-analytics 변수가 없다면 직접 만들수도 있습니다.

  _includes 폴더에 google-analytics.html로 파일을 생성합니다.
  아래의 소스를 복사해서 자신의 고유 추적 ID주소만 수정합니다.

```
<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
      (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
    m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
})(window,document,'script','//www.google-analytics.com/analytics.js','ga');

ga('create', 'UA-9104131-1', 'auto');
ga('send', 'pageview');

</script>

```

 ![img](/img/2018-08-22-Jekyll Google Analytics 등록/5.png)

 > _layout의 default.html에 가서 head 부분에
   {% include google-analytics.html %} 를 입력합니다.  

<br><br>

<a>기본적으로 Google Analytics 적용되어 구글 검색에 표시되려면 3일~2주가까이 소요됩니다.</a>

<br><br><br>
