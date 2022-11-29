프로젝트를 Build한 과정
=============

## 1. GitHub에서 Theme 다운 받기

- 나같은 경우 [여기](https://github.com/sergiokopplin/indigo) GitHub에서 indigo Theme을 다운 받았다.
- 이후 나의 Git Local 저장소에 파일을 풀어줬다.
- Theme이 잘 적용됐는지 확인하기 위해 **bundle exec jekyll serve** 명령어를 이용해 서버를 실행했다.

![sample](https://user-images.githubusercontent.com/105338988/204583212-6771a512-961e-46e6-bb25-5254663b1ddd.jpg)  

**다음 그림과 같이 테마가 잘 적용된 것을 확인할 수 있다.**

-----------------------------------

## 2. 가져온 Theme을 나의 blog에 맞게 수정

### _comfig.yml 파일을 수정 
1. title 내 이름으로 변경
2. bio 나에 맞게 변경
3. url을 나의 url로 변경
4. email 내 email로 변경
5. GitHub 이름 내 이름으로 변경
6. 그 외의 설정들을 나에게 맞게 설정
7. 사용하지 않는 설정 값을 지우거나 false 입력

![Screenshot_20221130_022146_Chrome](https://user-images.githubusercontent.com/105338988/204599576-6a2af73d-2f9d-4dd1-ae7b-14d32b0ed03b.jpg)  

**수정한 후의 모습**  
(사용하지 않는 About, Resume 삭제)

-------------------------------------

## 3. post 작성

- _posts 디렉토리 안에 원하는 post의 내용을 markdown 형태로 작성
- makrdown 파일 이름은 **년-월-일-파일이름.makrdown** 형태
- 나의 Theme에 맞는 post 작성 방법에 따라 다음과 같이 초기 설정 진행

```
---
title: "about me"
layout: post
date: 2022-11-25 3:23
headerImage: false
tag:
- kookmin univ.
- software
star: true
category: blog
author: Choi Seon woo 
---
```
- 위와 같이 title, date, category 등의 post에 대한 **정보** 입력
- serve를 실행해 post가 잘 올라갔나 확인

![스크린샷, 2022-11-30 02-42-55](https://user-images.githubusercontent.com/105338988/204603192-f81e649d-c5fb-463f-ab6a-b8aa2057645c.png)  
**post가 잘 된 것을 확인할 수 있다**

--------------------------------------------

## 3. post에 댓글 기능 추가

1. disqus 가입
2. disqus 셋팅
    - website name 셋팅
    - platform 중 jekyll 사용 표시
    - website url에 나의 git blog url 입력
3. _config.yml에 다음 코드 추가
```
comment:
  provider: "disqus"
  disqus:
    shortname: "내가 설정한 website name"
```  
4. dispus에서 Universal Code 복사
5. _layouts/post.html에 복사한 값 입력(나의 Theme에 맞게 설정)
6. post의 초기 설정 값에 **"comments: true"** 추가
```
---
title: "about me"
layout: post
date: 2022-11-25 3:23
headerImage: false
tag:
- kookmin univ.
- software
star: true
category: blog
author: Choi Seon woo 
comments: true
---
```
7. 댓글 작성 후 확인
![스크린샷, 2022-11-30 03-03-46](https://user-images.githubusercontent.com/105338988/204609961-e2ea4c77-f531-47b1-a174-a5086bb22f7b.png)  
**댓글이 잘 달리는 것을 확인할 수 있다.**

--------------------------------------------

## 4. Google Analytics 추가
1. google analytics 설정
    1. google analytics 계정 가입
    2. 관리자 항목의 data stream 항목에서 내 웹사이트를 등록한다.
    3. 생성된 측정 ID를 기억한다.

2. jekyll 설정
    1. _includes 폴더에 analytics.html 파일을 생성한다.
    2. analytics.html 파일에 아래의 코드를 추가한다.

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
    4. default.html의 head 태그 안에 아래의 코드를 추가한다.
    
    ```html
    {% raw %} {% include analytics.html %} {% endraw %}
    ```

3. 확인  
    google analytics에 들어가 데이터가 수집되는지 확인한다.

    ![스크린샷, 2022-11-29 19-34-44](https://user-images.githubusercontent.com/105338988/204507510-999f96f9-34b8-4ffc-bd96-2a4adcb574ed.png)

-------------------------------

## 5. favicon 추가

1. _includes/favicon.html 파일 생성
2. 아래의 코드 추가
``` html
<link rel="apple-touch-icon-precomposed" sizes="16x16" href="{{ site.url }}/사진파일경로" />
<link rel="apple-touch-icon-precomposed" sizes="32x32" href="{{ site.url }}/사진파일경로" />
<link rel="apple-touch-icon-precomposed" sizes="96x96" href="{{ site.url }}/사진파일경로" />
<link rel="icon" type="image/png" href="{{ site.url }}/사진파일경로" sizes="96x96" />
<link rel="icon" type="image/png" href="{{ site.url }}/사진파일경로" sizes="32x32" />
<link rel="icon" type="image/png" href="{{ site.url }}/사진파일경로" sizes="16x16" />
<meta name="application-name" content="&nbsp;"/>
<meta name="msapplication-TileColor" content="#FFFFFF" />
<meta name="msapplication-TileImage" content="mstile-144x144.png" />
<meta name="msapplication-square70x70logo" content="mstile-70x70.png" />
<meta name="msapplication-square150x150logo" content="mstile-150x150.png" />
<meta name="msapplication-wide310x150logo" content="mstile-310x150.png" />
<meta name="msapplication-square310x310logo" content="mstile-310x310.png" />
```
3. _layouts/default.html 파일 안의 head 태그 안에 **{% include favicon.html %}** 입력
4. favion 추가됐는지 확인  
![스크린샷, 2022-11-30 03-23-57](https://user-images.githubusercontent.com/105338988/204614521-43816d7b-8120-4493-a499-b9b85ff6a598.png)   

