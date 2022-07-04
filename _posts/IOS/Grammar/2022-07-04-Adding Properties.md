---
title: Adding Properties
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Adding Properties
- 계산 속성

~~~
extension Date {
  var year: Int {
    let cal = Calendar.current
    return cal.component(.year, from: self)
  }
}

let today = Date()
today.year
~~~
이렇게 구조체에서는 계산속성만 확장에서 사용할 수 있다.