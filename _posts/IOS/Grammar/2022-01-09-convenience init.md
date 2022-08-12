---
title: "convenience init"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## convenience init  

~~~
//친구 클래스
class Friend {
  var name : String
  var age : Int

  //지정 생성자메소드 designated initializer
  init(name: String) {
    self.name = name
    self.age = 10
  }

  // 컨비니언스 이닛을 통해 기존 지정 생성자에 추가적으로 작업이 가능하다.
  convenience init(name: String, age: Int) {
    //!중요 컨비니언스 생성자는 최소 지정 생성자메소드 중 하나를 호출 해야한다.
    //지정 생성자 호출
    self.init(name: name)

    //추가적으로 원하는 설정
    self.age = age
  }
}

let myFriend = Friend(name: "철수")
print("\(myFriend.name) / \(myFriend.age)")

let bestFriend = Friend(name: "제임스", age: 30)
print("\(bestFriend.name) / \(bestFriend.age)")
~~~  

출력  
~~~
철수 / 10
제임스 / 30
~~~  