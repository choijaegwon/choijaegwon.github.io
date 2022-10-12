---
title: Protocol compostition

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Protocol compostition  

~~~
protocol Resettable {
  func reset()
}

protocol Printable {
  func printValue()
}

class Size: Resettable, Printable {
  var width = 0.0
  var height = 0.0

  func reset() {
    width = 0.0
    height = 0.0
  }

  func printValue() {
    print(width, height)
  }
}

class Circle: Resettable {
  var radius = 0.0

  func reset() {
    radius = 0.0
  }
}

class Oval: Circle {

}

let r: Resettable = Size()
let p: Printable = Size()
~~~
r과 P 는 각각 Resettable 과 Printabl를 구현한다. 하지만 동시에 구현받을수없을까? 
둘다 사용하려면? &를 사용하면 된다.

~~~
var rp: Resettable & Printable = Size()
~~~
하지만
~~~
rp = Circel() //오류가 발생한다.
~~~
그 이유는 Circle에서는 Printable이 없기 떄문이다.