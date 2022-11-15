---
title: Protocol Extension

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Protocol Extension  
- 프로토콜 확장


~~~
protocol Figure {
  var name: String { get }
  func draw()
}

extension Figure {
  func draw() {
    print("draw figure")
  }
}

struct Rectangle: Figure {
  var name = ""
}

let r = Rectangle()
r.draw()
~~~
위 extension Figure에서 draw()메서드가 있어가지고 밑에 struct에서 name만 선언해줘도 된다.  
만약에 struct에서 draw()를 직접적으로 구현을하면 그 구현한것이 우선순위를 가진다.

