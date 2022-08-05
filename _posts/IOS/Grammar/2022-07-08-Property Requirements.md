---
title: Property Requirements
categories:
  - IOSGrammar
  
tags:
  - IOS
  - Swift
---

# Property Requirements
- 내용이 뭐가 들어가든 상관은 없다
- 최소한의 요구사항이기 때문에 추가로 더해도 된다.

기본
~~~
protocol ProtocolName {
  var name: Type { get set }
  static var name: Type { get set }
}
~~~

활용  
~~~
protocol Figure {
  var name: String { get }
}

struct Rectangel: Figure {
  var name = "Rect"
}

struct Triangle: Figure {
  var name = "Triangle"
}

struct Circle: Figure {
  var name: String {
    return "Circle"
  }
}
~~~