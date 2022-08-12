---
title: Initializer Syntax
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Initializer Syntax  

기본형태
~~~
init(parameters) {
  statements
}
~~~
  
활용
~~~
class Position {
  var x: Double
  var y: Double

  init() {
    x = 0.0
    y = 0.0
  }

  init(value: Double) {
    x = value
    y = value
  }
}

let a = Position()
a.x // 0
a.y // 0

let b = Position(value: 100)
b.x // 100
b.y // 100
~~~
init초기화란 인스턴스를 찍을때 필요한 문법이다.  
초기화를 해줘야지 처음 값을 세팅할때 값이 들어 갈 수 있다.  
