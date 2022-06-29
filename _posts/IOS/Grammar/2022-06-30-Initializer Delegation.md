---
title: Initializer Delegation
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Initializer Delegation  
- 값형식은 상속이 불가능하다

값형식(Struct)
~~~
struct Size {
  var width: Double
  var height: Double

  init(w: Dobule, h: Dobule) {
    width = w
    height = h
  }

  init(value: Double) {
      self.init(w: value, h: value)
  }
}
~~~
2속성을 모두 초기화 하고 있다. 두번째 init이 첫번쨰 init에게 위임을 하고있다. 이게 바로 Delegation이다.  
이러면 첫번째 init만 바꿔주면 되서 유지보수가 편해진다.  

참조형식(class)
~~~
class Figure {
  let name: String

  init(name: String) {
    self.name = name
  }

  convenience init() {
    self.init(name: "unknown")
  }
}

class Rectangle: Figure {
  var width = 0.0
  var height = 0.0

  init(n: String, w:Double, h: DOuble){
    weidth = w
    height = h
    super.init(name: n)
  }

  convenience init(value: Double) {
    self. init(n: "rect", w: value, h: value)
  }
}

class square: Rectangle {
  convenience init(value: Double) {
    self.init(m: "square", w: value, h: value)
  }

  convenience init() {
    self.init(value: 0.0)
  }
}
~~~
이렇게 상위 클래스에 위임을 하며 클래스를 상속하면, 유지보수하기가 더 편해진다.
