---
title: Type Conversion

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

메모리에 저장한된 값을 다른형식으로 바꿔서 새로운 값을 생성한다.  

~~~
let a = 123
let b = 4.56

// a + b -> 에러가 발생됨

Double(a) + b // 123.0 + 4.56
a + Int(b) // 123 + 4
~~~

출력
~~~
127.56
127
~~~
