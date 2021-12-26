---
title: "typealias"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## typealias  

~~~
protocol Naming {
  func getName() -> String
}
protocol Aging{
  func getAge() -> Int
}
// typealias 별칭을 통해 프로토콜 별명 설정이 가능하다.
typealias Friendable = Naming & Aging

struct Friend : Friendable {
  var name : String
  var age : Int
  func getName() -> String{
    return self.name
  }
  func getAge() -> Int {
    return self.age
  }
}
// 자료형, 클래스, 스트럭트, 클로저 등 모두 별명설정이 가능하다.
typealias FriendName = String

var friendName : FriendName = "최재권"

// 친구 배열을 별명으로 설정하였다.
typealias Friends = [Friend]

var myFriendsArray = Friends()

// 클로저를ㄹ StringBlock 이라는 멸명으로 설정하였다.
typealias StringBlock = (String) -> Void

func sayHi(completion : StringBlock){
  print("안녕하세요?!")
  completion("오늘도 고생하셨습니다!")
}
sayHi(completion: { result in
  print("여기서 받음 : ", result)
})
~~~

