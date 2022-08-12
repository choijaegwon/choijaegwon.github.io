---
title: Raw Values

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Enumeration Types

## Raw Values

~~~
enum Alignment {
  case left
  case right
  case center
}
~~~
원시값을 넣을 수 있다.  

~~~
enum Alignment: Int {
  case left = 0
  case right
  case center
}
~~~
이렇게 생성하면 자동으로 right = 1 center에는 2가 들어간다.  
즉 자동으로 1 씩 증가한다. 기본값은 0이다.
