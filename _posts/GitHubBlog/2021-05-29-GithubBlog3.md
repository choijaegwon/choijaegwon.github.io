---
title: "M1 Mac에서 github.io 블로그 관리하기"

categories:
  - GitHubBlog
tags:
  - Ruby
  - Jekyll
  - Programming
  - GitHub Pages
---
## 1. Visual Studio 설치하기
- <https://visualstudio.microsoft.com/ko/downloads/>

우선 코드를 편하게 관리하기 위해서 맥북에 Visual Studio를 설치해준다.

## 2. 전에 생성한 username.github.io 폴더를 연다
_posts 폴더에 yyyy-mm-dd-파일이름.md 형식으로 파일을 만들어 준다.  
ex) 2021-05-29-github.md
그후 
~~~
---
title: "github.io 블로그 첫 포스팅입니다"
excerpt: "Github Blog글을 처음 써보며."

categorise:
  - Blog
tags:
  - Blog
---
여기엔 Markdown문법으로 적으면 된다.
나는 블로그를 만들었을때 시간이 많이 들었지만, 다른사람들은 이글을 보고
조금 더 빨리 만들었으면 좋겠다.
~~~
이런식으로 적고 git push로 GitHub에 올려주면, 포스팅이 된다.   
하지만, 보통 push를 하면 1~3분 정도 걸리니 그전에 확인하는게 좋다.
그래서 설치한것이 전에 포스팅한 Ruby와 Jekyll이다.



## 3. 내 맥북에서 블로그 미리보기!
Visual Studio에서 github와 연결된 내 폴더를 열어준다.
밑에 터미널을 열고,
~~~
bundle exec jekyll serve
~~~
을 실행시켜 주면, <http://localhost:4000/>를 통해서,
내 블로그를 깃허브에 올리기전에 미리 보면서 수정할 수 있다.