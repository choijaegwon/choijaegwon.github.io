---
title: Extension-Syntax
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Extension-Syntax  
- 확장
- 수평확장이라고 생각하면 된다.
- 새로운 메서드를 추가할 수 있따.

~~~
struct Size {
  var width = 0.0
  var height = 0.0
}

extension Size {
  var area: Double {
    return width * height
  }
}

let s = Size()
s.width
s.height
s.area 
~~~
이렇게 확장에서 변수를 확장하려면 계산속성만 추가할 수 있다.  
