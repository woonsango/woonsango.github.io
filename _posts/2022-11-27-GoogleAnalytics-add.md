<!-- ---
title: "GoogleAnalytics 추가 방법"
layout: post
date: 2022-11-27 3:23
headerImage: false
tag:
- googleanalytics
- jekyll
category: blog
author: Choi Seon woo
contents: true
---

#### Elements
- [Google-analytics](#google-analytics)
- [추가방법](#추가방법)

---

## Google-analytics

google analytics는 구글이 제공하는 웹 애널리틱스 서비스이다.
웹 애널리틱스는 웹 사용률을 이해하고 최적화하기 위해 웹 데이터를 특정하고 수집하고 분석하는 것을 말한다.

---

## 추가방법
1. google analytics 설정
    1. google analytics 계정 가입
    2. 관리자 항목의 data stream 항목에서 내 웹사이트를 등록한다.
    3. 생성된 측정 ID를 기억한다.

2. jekyll 설정
    1. _includes 폴더에 analytics.html 파일을 생성한다.
    2. analytics.html 파일에 다음의 내용을 추가한다.

    ```html
    <script async src="https://www.googletagmanager.com/gtag/js?id=측정ID"></script>
    <script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());

    gtag('config', '{{ site.analytics-google }}');
    </script>
    ``` 

    3. 측정ID라고 써져있는 곳에 자신의 측정ID를 입력한다.
    4. default.html의 head 태그 안에 다음의 코드를 추가한다.
    
    ```html
    {% raw %} {% include analytics.html %} {% endraw %}
    ```

3. 확인  
    google analytics에 들어가 데이터가 수집되는지 확인한다.

    ![스크린샷, 2022-11-29 19-34-44](https://user-images.githubusercontent.com/105338988/204507510-999f96f9-34b8-4ffc-bd96-2a4adcb574ed.png) -->
