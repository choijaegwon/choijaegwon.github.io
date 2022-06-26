---
title: Nested Types
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Nested Types
- 다른형식내부에서 선언하면 Nested Type으로 선언된다.

~~~
class One {
  struct Two {
    enum Three {
      case a

      class Four {

      }
    }
  }

  var a = Two()
}
~~~
  
~~~
let tow: Two = Two()
~~~
이렇게 사용하면 에러가 뜬다.  

~~~
let tow: One.Two = Two()
~~~
이렇게 사용해야한다.
