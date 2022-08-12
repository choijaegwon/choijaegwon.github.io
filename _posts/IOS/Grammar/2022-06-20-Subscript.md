---
title: Subscript
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Subscript  
- []가 Subsript다.
- 직접 구현이 가능하다.  
- get블록은 생략이 불가능하지만, set블록은 생략이 가능하다.

~~~
let list = ["A", "B", "C"]
list[0] // []가 서브스크립트.
~~~

기본
~~~
subscript(parameters) -> ReturnType {
  get {
    return expression
  }
  set(name) {
    statements
  }
}
~~~

활용
~~~
class List {
  var data = [1, 2, 3]

  subscript(index: Int) -> Int {
    get {
      return data[index]
    }
    set {
      data[index] = newValue
    }
  }
}

var l = List()
l[0] // get블록실행
l[1] = 123 // set블록실행
~~~
하나의 parameter를 받기 떄문에 하나만 받을 수 있다.