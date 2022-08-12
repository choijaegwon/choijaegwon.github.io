---
title: Protocol Syntax
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Protocol Syntax  
- 형식에서 공통의로 구현해야하는 구문
- 반드시 모두 구현해야한다
- 요구사항이라고도 한다
- 상속을 지원한다.

기본
~~~
protocol ProtocolName {
  propertyRequirements
  methodRequirements
  initializerRequirements
  subscriptRequirements
}

protocol ProtocolName: Protocol, ... {

}
~~~  

활용
~~~
protocol Something {
  func doSomething()
}

struct Size: Something {
  
  // 필수적으로 구현해야됨
  func doSomething() {
    // 필요한 내용적기
  }
}
~~~