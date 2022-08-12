---
title: Deinitializer
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Deinitializer  
- 소멸자
- deinit
- 구현되어 있지않으면 자동으로 생성한다.

~~~
class Size {
  var width = 0.0
  var height = 0.0
}

class Position {
  var x = 0.0
  var y = 0.0
}

class Rect {
  var origin = Position()
  var size = Size()

  deinit {
    print("deinit \(self)")
  }
}

var r: Rect? = Rect()
r = nil //deinit이 호출되며 소멸자가 실행된다.
~~~