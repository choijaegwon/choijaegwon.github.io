---
title: Computed Property
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Computed Property
- 계산 속성
- get과 set을 사용해야하는데 get은 필수이다.
- 자료형을 명시적으로 작성해야한다.

~~~
class Person {
  var name: String
  var yearOfBirth: Int

  init(name: String, year: Int) {
    self.name = name
    self.yearOfBirth = year
  }

  var age: Int {
    get {
      let calendar = Calendar.current
      let now = Date()
      let year = calendar.component(.year, from: now)
      return year - yearOfBirth
    }
    set {
      let calenar = Calenar.current
      let now = Date()
      let year = calendar.component(.year, from: now)
      yearOfBirth = year - newValue
    }
  }
}

let p = Pserson(name: "Jogn Doe", year: 2002)
p.age // get블록실행
p.age = 50 //set블록이 실행된다
~~~

