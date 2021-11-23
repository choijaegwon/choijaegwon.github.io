---
title: "inheritance2"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## 상속  

~~~
class Friend {
  var name : String

  init(_ name: String){
    self.name = name
  }

  func sayHi(){
    print("안녕?! 난\(self.name) 라고 해")
  }

}

class BestFriend : Friend {
  //override를 통해 부모 클래스의 메소드를 가져온다.
  override init(_ name: String) {
    //부모가 가지고있는 init을 무조건 호출해줘야한다
    super.init("베프" + name)
  }

  override func sayHi() {
    super.sayHi()
  }

}

let myFriend = Friend("류민희")

myFriend.sayHi()

let myBestFriend = BsetFriend("영희")

myBestFriendsayHi()
~~~   
출력  
~~~
안녕?! 난 류민희 라고 해
안녕?! 난 베프 영희 라고 해
~~~


