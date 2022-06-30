---
title: Failable initializer
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Failable initializer  

기본
~~~
init?(parameters) {
  initialization
}

init!(parameters) {
    initialization
}
~~~

활용
~~~
struct Position {
  let x: Double
  let y: Double

  init?(x: Double, y: Double) {
    guard x >= 0.0, y >= 0.0 else { return nil }

    self.x = x
    self.y = y
  }

    init!(value: Double) {
    guard value >= 0.0 else { return nil }

    self.x = value
    self.y = value
  }
}

//올바르게 생성된다
var a = Position(x:12, y: 35)
a = Position(x: -12, y: 0) // nil을 리턴한다


var b = Position(value: 12) //정상적으로 작동한다
b = Position(value: -12) //nil을 리턴한다 초기화에 실패 errer가 발생함.
~~~