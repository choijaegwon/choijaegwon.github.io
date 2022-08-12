---
title: Inheritance
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Inheritance
- 상속

기본
~~~
class ClassName: SuperClassName {

}
~~~

활용
~~~
class Figure {
  var name = "Unknown"

  init(name: String) {
    self.name = name
  }

  func draw() {
    print("draw \(name)")
  }
}

class Circle: Figure {
  var radius = 0.0
}

let c = Circle(name: "Circle")
c.radius
c.name
c.draw()
~~~
상속을 받았기 때문에, c.name, c.draw() 속성과 메서드둘다 사용이 가능하다.