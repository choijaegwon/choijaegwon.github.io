---
title: Type Castring
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Type Castring
- 표현식 is 타입
- 추후 다형성과 연관되서 사용할 수 있다.

기본
~~~
expression is Type
~~~

활용
~~~
let num = 123

num is Int // true
num is Double // false

let nsstr = "str" as NSString // 캐스팅 성공
~~~

 