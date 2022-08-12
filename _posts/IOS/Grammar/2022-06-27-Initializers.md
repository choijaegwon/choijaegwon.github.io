---
title: Initializers
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Initializers  
- 생성자
- 구조체, 열거형, 클래스는 인스턴스를 만들 수 있다.

~~~
class Position {
  var x = 0.0
  var y: Double
  var z: Double? = nil
}
~~~
이렇게 사용이 가능하다.
~~~
let p = Position()
~~~
아무것도 생성하지 않았다면, 컴파일러가 자동으로 만들어준다.  

~~~
class SizeObj {
  var width = 0.0
  var height = 0.0

  init(width: Double, height: DOuble) {
    self.width = width
    self.height = height
  }

  convenicence init(value: DOuble) {
    sefl.init(width: value, height: value)
  }
}
~~~
convenicence는 기본 init을 포함하고 있다.
