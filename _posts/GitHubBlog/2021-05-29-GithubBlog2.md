---
title: "M1 Mac에서 github.io 블로그만들기"

categories:
  - GitHubBlog
tags:
  - Ruby
  - Jekyll
  - Programming
  - GitHub Pages
---
## 1. Github 에서 블로그 용으로 사용할 Repository를 생성해준다.
 ![image](https://user-images.githubusercontent.com/68246962/120060867-2c403e80-c095-11eb-85cf-75fac2c3ba4a.png)
레포지토리의 이름은 자신의 깃허브 `username.github.io` 로 생성해준다.

## 2. 생성한 Repository를 Local 환경으로 Clone해 온다.
자신이 블로그를 관리할 폴더를 하나 만들고, 거기에 git clone명령어를 사용해 복사해 오면 된다.  물론 .zip 으로 받아서 압축을 풀고 연결해도 상관은 없다. 폴더안에 `username.github.io` 폴더가 생겼을 것이다.


## 3. jekyll 테마를 내 블로그 레포지토리 Local 폴더에 다운받는다.  
테마는 굉장히 다양한 것들이 많다. 멋있는 개발자분들이 공유를 해주신걸 바로 가져와서 사용해도 된다.

- <http://jekyllthemes.org/>
- <http://themes.jekyllrc.org/>
- <https://jekyllthemes.io/>

나의 경우 우선 혼자서 공부하면서, 정리하는 그런 블로그를 만들고 싶어서  
무료 theme인 [minimal-mistakes](https://github.com/mmistakes/minimal-mistakes "minimal-mistakes")를 사용했다.   
지금 보이는 이블로그가 minimal-mistakes테마 이다.  
테마의 압축을 풀어주고, 테마의 내용물을 전부다 복사하여

clone 했던 내 블로그 레포지토리 폴더 `깃허브아이디.github.io` 위치에 전부 붙여넣기 해준다. 

## 4. Github Pages 서버와 연결해주기
터미널을 실행하고 cd명령어를 통해`깃허브아이디.github.io`폴더에 들어간 후 
~~~
git add .
git commit -m "커밋 메세지"
git push origin master
~~~
위에 명령어를 순서대로 실행하면 된다.  
또는 [Githubdesktop](https://desktop.github.com/ "Githubdesktop")를 사용하여 관리해주면 된다.

그리고 이제 https://깃허브아이디.github.io에 접속하면, 테마가 적용된 자신의 블로그를 확인 할 수 있다.(반영되는데 1~3분 정도 시간소요가 된다.)