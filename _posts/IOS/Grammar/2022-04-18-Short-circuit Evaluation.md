---
title: Short-circuit Evaluation

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# 단락평가

~~~
var a = 1
var b = 1

func updateLeft() -> Bool {
  a +=1
  return true
}

func updateRight() -> Bool {
  b += 1
  return true
}

if updateLeft() || updateRight() {
  // updateRight는 실행되지 않는다. -> 이미 결과값을 얻었기떄문.
}
a // 2
b // 1
~~~

다른예제를 보면, 

~~~
var a = 1
var b = 1

func updateLeft() -> Bool {
  a +=1
  return falase
}

func updateRight() -> Bool {
  b += 1
  return true
}

if updateLeft() || updateRight() {
  // updateLeft가 false라서 updateRight까지 실행된다
}
a // 2
b // 2
~~~