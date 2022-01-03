---
title: "class func"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## class func  

~~~
// 친구 클래스
class Friend {

  // 일반적인 메소드
  func sayHi() {
    print("안녕?!")
  }

  // 클래스 메소드로 해당 인스턴스가 생성되지 않아도 호출가능
  class func sayBye() {
    print("바이바이~!")
  }
}

// 일반적인 형태는 인스턴스를 생성해야 해당 메소드 호출이 가능하다.
let myFriend = Friend()
myFriend.sayHi()

// 인스턴스를 생성하지 않아도 바로 클래스에 접근이 가능하다.
Friend.sayBye()
~~~   

출력
~~~
안녕?!
바이바이~!
~~~  
