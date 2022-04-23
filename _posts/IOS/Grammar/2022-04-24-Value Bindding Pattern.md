---
title: Value Bindding Pattern

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Value Bindding Pattern

- 바인딩된 변수는 안에서만 사용할 수 있다. 
- 주로 where절과 함께 사용한다.
~~~
let a = 1

switch a {
  case let x:
   print(x)
}
~~~
실행

~~~
1
~~~
다른 코드를 보면

~~~
let pt = (1,2)

switch pt {
  case let(x,y):
    print(x,y)
  case (let x, let y):
    print(x, y)
  case let(x, _):
    print(x)
}
~~~
이렇게 사용할 것만 사용하고 안할건 _를 써주면 된다.