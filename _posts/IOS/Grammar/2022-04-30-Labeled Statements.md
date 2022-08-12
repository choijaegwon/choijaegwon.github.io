---
title: Labeled Statements

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Labeled Statements
- 라벨을 이용해 가까운 함수말고 멀리있는 함수도 제어할 수 있다.

~~~
outer: for i in 1...3 {
  print("OUTER LOOP", i)

  for j in 1...3 {
    print(" inner loop", j)

    break outer
  }
}
~~~
이렇게 사용하면 밖에있는 문장에 제어가된다.