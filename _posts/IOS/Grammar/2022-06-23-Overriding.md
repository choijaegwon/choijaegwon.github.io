---
title: Overriding
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Overriding
- 재정의 
- 상위 클래스에서 정의된 메서드나 변수를 재정의 할 수 있다.

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

  // 재정의
    override func draw() {
    super.draw()
    print("짠")
  }

}

let c = Circle(name: "Circle")
c.draw() 
~~~

출력
~~~
draw Circle
짠
~~~
이렇게 상위 클래스에서 정의한 메서드를 하위 클래스에서 재정의하여 사용할 수 있다.