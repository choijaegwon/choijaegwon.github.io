---
title: Required Initializer
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Required Initializer 
- 필수 생성자

~~~
class Figure {
  var name: String

  required init(name: String) {
    self.name = name
  }

  func draw() {
    print("draw \(name)")
  }
}

class Rectangle: Figure {
  var width = 0.0
  var height = 0.0

  Init() {
    width = 0.0
    height = 0.0
    super.init(nanme: "unknown")
  }

  required init(name: String) {
    width = 0.0
    height = 0.0
    super.init(name: name)
  }
}
~~~
이렇게 Required가 적혀 있으면 상속을 받을때 Required Initializer가 적힌 생성자를 반드시 구현해 줘야한다.