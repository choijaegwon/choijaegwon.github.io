---
title: Argument Label

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Argument Label
- 함수이름의 가독성을 높이기 위해서 사용한다.

~~~
func sayHello(to: String = "Stranger") {
  print("Hello, \(to)")
}

sayHello(to: "Swift")

func sayHello(to name: String) {
  print("Hello, \(name)")
}
~~~
실행을 해보면, 에러는 발생하지 않는다 그 이유는 무엇일까?  
바로 함수 이름에 Argument Label(to)가 추가되었기 때문이다.  

~~~
func sayHello(to name: String) {
  print("Hello, \(name)")
}

sayHello(to: "Swift") // Hello,Swift
sayHello(name: "Swift") // 에러가 발생한다.
~~~
#
~~~
func sayHello(_ name: String) {
  print("Hello, \(name)")
}

sayHello("Swift")
~~~
함수에서 Argument Label을 생략했다면, 함수를 호출할때도 생략 해야한다.  
Argument Label은 주로 전치사가 온다.
