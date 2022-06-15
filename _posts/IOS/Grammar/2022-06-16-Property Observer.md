---
title: Property Observer
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Property Observer  
- 속성감시자
- 속성을 감시한다.

기본
~~~
willSet(){}
didSet(){}
~~~
willSet은 newValue,  
didSet은 oldVaule로 파라미터를 받는다.

~~~
class Size {
  var width = 0.0 {
    willSet {
      print(width, "=>", newValue)
    }
    didSet {
      print(oldVaule, "=>", width)
    }
  }
}

let s = Size()
s.width = 123
~~~
출력하면
~~~
0.0 => 123.0
0.0 => 123.0
~~~
willSet은 속성이 변하기 전을 의미하고 didset은 속성이 변한 후 를 의미한다.   


