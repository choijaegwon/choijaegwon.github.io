---
title: Adding Subscripts
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Adding Subscripts

몇번인덱스에 어떤 문자가 들어있는지 알려주는 subscript 확장한 프로그램
~~~
extension String {
  subscript(idx: Int) -> String? {
    guard (0..<count).countains(idx) else {
      return nil
    }

    let target = index(startIndex, offsetBy: idx)
    return String(self[target])
  }
}

let str = "Swift"
str[1] // w
str[100] // nil
~~~

날짜를 가져와서 년도가 몇년도인지 subscript를 이용하여 확장한 프로그램
~~~
extension Date {
  subscript(componet: Calendar.Component) -> Int? {
    let cal = Calenar.current
    return cal.component(component, from: self)
  }
}

let today = Date()
today[.year] //2022
~~~
