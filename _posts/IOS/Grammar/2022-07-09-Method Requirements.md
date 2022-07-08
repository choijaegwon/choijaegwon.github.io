---
title: Method Requirements
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Method Requirements  
- 구조체에서는 mutating 키워드를 사용해야지 메서드를 사용할 수 있다.

기본
~~~
protocol ProtocelName {
  func name(param) -> ReturnType
  static func name(param) -> ReturnType
  mutating func name(param) -> ReturnType
}
~~~
  

활용
~~~
protocol Resettable {
  func reset()
}

class Size: Resettable {
  var width = 0.0
  var height = 0.0

  func reset() {
    width = 0.0
    height = 0.0
  }
}
~~~

하지만 구조체에서는

protocol Resettable {
  mutating func reset()
}

struct Size: Resettable {
  var width = 0.0
  var height = 0.0

  mutating func reset() {
    width = 0.0
    height = 0.0
  }
}
~~~
이렇게 사용해야한다.