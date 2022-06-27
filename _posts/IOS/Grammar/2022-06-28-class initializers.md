---
title: class initializers
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# class initializers  
- 지정생성자와 간편생성자가 있다.

~~~
class Position {
  var x: Double
  var y: Double

  init(x: Double, y: Double) {
    self.x = x
    self.y = y
  }
}
~~~
이렇게 사용할 수있다. 하지만 이런 기본생성자는 설정을 안해줘도  
컴파일러에서 자동으로 생성해준다.

~~~
class Position {
  var x: Double
  var y: Double

  init(x: Double, y: Double) {
    self.x = x
    self.y = y
  }

  convenicence init(x: Double) {
    self.init(x: y, y: 0.0)
  }
}
~~~
이렇게 사용도 가능하다.
