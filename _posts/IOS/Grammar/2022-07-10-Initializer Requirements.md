---
title: Initializer Requirements
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Initializer Requirements
- 

기본
~~~
protocol ProtocolName {
  init(param)
  init?(param)
  init!(param)
}
~~~

활용
~~~
protocol Figure {
  var name: String { get }
  init(name: String)
}

struct Rectangle: Figure {
  var name: String
}
~~~
멤버이니셜 라이저가 자동으로 생성된다. 때문에 자동으로 생성자를 만들어줘서 프로토콜의 생성자요구치를 충족시킨다.  
~~~
protocol Figure {
  var name: String { get }
  init(name: String)
}

class Rectangle: Figure {
  var name: String
  
  required init(name: String) {
    self.name = name
  }
}
~~~
class에서는 상속을 고려해야한다. 떄문에 required로 구현해야한다.  

