---
title: Optional Requirements

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Optional Requirements  
- 선택적 요구사항 선언
- class전용이다.

기본
~~~
@objc protocol  ProtocolName {
  @objc optional requirements
}
~~~

활용
~~~
@objc protocol Drawable {
  @objc optional var strokeWidth: Double { get set }
  @objc optional var strokeColor: UIColor { get set }
  func draw()
  @objc optionl func reset()
}


class Rectangle: Drawable {
  func draw() {
  }
}

let r: Drawable = Rectangle()
r.draw() 
~~~
이렇게 필수적인것만 사용할 수 있다. 부를순 있지만 nil를 return한다.