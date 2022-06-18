---
title: Type Method
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Type Method  
- 클래스, 구조체, 열거형에서 사용이 가능하다.  

~~~
class Circle {
  static let pi = 3.14
  var radius = 0.0

  func getArea() -> Double {
    return radius * radius * Circle.pi
  }

  static func PrintPi() {
    print(pi)
  }
}

Circle.printPi() // 3.14
~~~
Circle.pi처럼 static 키워드가 붙으면 클래스이름까지 불러줘야 접근이 가능해진다.  
