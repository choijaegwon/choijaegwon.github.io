---
title: Protocol Types

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Protocol Types  

~~~
protocol Resettable {
  func reset()
}

class Size: Resettable {
  var width = 0.0
  var height = 0.0

  func reset() {
    weidth = 0.0
    height = 0.0
  }
}

let s = size() //width와 height사용 가능
let r: Resttable = Size() //width와 height를 사용할 수없다 타입이 Resttable이기 때문이다.
r.reset //사용가능
~~~
  
~~~
instance is ProtocolName
~~~
왼쪽 Instance가 ProtocolName을 채용하고 있다면 true를 return 한다.
