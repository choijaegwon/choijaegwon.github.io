---
title: continue Statement

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# continue 
- 반복문에서만 사용한다
- 현재의 반복을 중지하고 다음 반복을 시작한다.

~~~
for index in 1...10 {

  if index % 2 == 0 {
    coutinue
  }

  print(index)
}
~~~
출력
~~~
1
3
5
7
9
~~~

