---
title: Ternary Conditional Operator

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# 삼항 연산자

~~~
let hour = 12

hour < 12 ? "am" : "pm" // -> "pm"
~~~
- 분리표현식이 와야한다.
- 2번쨰 피연산자와 3번째 피연산자의 자료형이 같아야한다.  

~~~
if hour < 12 {
  "am"
} else {
  "pm
}
~~~
출력
~~~
"pm"
~~~
