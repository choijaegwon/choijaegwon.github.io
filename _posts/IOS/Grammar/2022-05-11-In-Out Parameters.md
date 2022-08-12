---
title: In-Out Parameters

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# In-Out Parameters
- 입출력 파라미터
- 변수의 값을 직접 바꿀 수 있다.
- &가 붙어야 한다.

~~~
var num1 = 12
var num2 = 34

func swapNumber(_ a: inout Int, with b: inout Int) {
  let tmp = a
  a = b
  b = tmp
}

num1 //12
num2 //34

swapNumber(&num1, with: &num2)

num1 //34
num2 //12
~~~
입출력파라미터를 사용하면 값 자체를 바꿀 수 있다.