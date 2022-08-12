---
title: Logical Operators

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# 논리연산자

## !  
- 참은 거짓으로 만들고 거짓은 참으로 만든다.

~~~
!true // -> false
~~~  

## &&
- 모든 연산자가 true여야 true가 trye를 리턴한다.

~~~
a > 30 && b % 2 == 0

true && true // -> true
true && false // -> false
false && trye // -> false
false && false // -> false
~~~

## ||
- 하나만 true면 true이다.

~~~
a > 30 || b % 2 == 0

true && true // -> true
true && false // -> true
false && trye // -> true
false && false // -> false
~~~