---
title: Subscript Requirements
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Subscript Requirements  

기본
~~~
protocol ProtocolName {
  subscript(param) -> ReturnType { get set }
}
~~~

활용
~~~
protocol List {
  subscript(idx: Int) -> Int { get }
}

struct DataStore: List {
  subscript(idx: Int) -> Int {
    return 0
  }
}
~~~
서브 스크립트도 프로토콜을 상속받을 수 있다.