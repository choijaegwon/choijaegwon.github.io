---
title: Enumeration Types

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## Enumeration Types

~~~
let left = 0 
let center = 1
let right = 2

var alignment = center //1
~~~
-> 0, 1, 2 가 어떻게 사용되는지 알 수 없어서 가독성이 매우 안좋다.  
갑자기 123을 넣어도 상관이 없어진다. 따라서 Enumeration Types을 사용해야한다.  

~~~
enum Alignment {
  case left
  case center
  case right
}

Alignment.center
~~~
이렇게 사용하면 바로 center인지 알 수 있게된다. 가독성이 좋아진다.