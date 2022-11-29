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
사용하지 않는 About, Resume 삭제

-------------------------------------
