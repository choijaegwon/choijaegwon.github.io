---
title: Structures and Classes

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Structures and Classes

## struct

~~~
struct Person {
  var name: String
  var age: Int

  func speak() {
    print("Hello")
  }
}
~~~
구조체는 값타입이고, 스택에만 존재한다.
~~~
let p = Person(name: "Steve", age: 50)

p.name // "Steve"
p.age // 50
~~~
구조체로 인스턴스화 시키고 구조체 안에 name과 age에 접근하려면  
p.name, p.age등 으로 접근해야한다.  

## class

~~~
class Pserson {
  var name = "John Doe"
  var age = 0

  func speak() {
    print("Hello")
  }
}

let p = Person()
p.name // "John Doe"
p.age // 0
p.speak() // "Hello"
~~~
class는 struct와 똑같이 구현이 가능하다.  
하지만, class는 힙 영역에 올라가고 참조 타입이여가지고 좀 더 길게 메모리영역에 남는다.  
