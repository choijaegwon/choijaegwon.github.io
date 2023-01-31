---
title: "싱글톤 패턴(Singleton Pattern)2"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# 싱글톤 패턴(Singleton Pattern)2
전 글을 읽어서 정리해보자면
- 어느 클래스에서 접근 가능하게한 객체  

이정도로 정리해 볼 수 있을 것 같다.  
그러면 어디서든 접근한다라는 특별한 기능을 가지려면 특별하게 만들어줘야하는데 어떻게 구현해야 하는걸까?  

# Singleton Class 만드는 방법
## static 프로퍼티로 Instance 생성하기
~~~
class UserInfo {
    static let shared = UserInfo()

    var id: String?
    var password: String?
    var name: String?
}
~~~
이런식으로 static을 사용하여 Instance를 저장할 프로퍼티를 하나 생성해 주는 것이다.

## nit 함수 접근제어자를 private로 지정하기
~~~
class UserInfo {
    static let shared = UserInfo()

    var id: String?
    var password: String?
    var name: String?

    private init() { }
}
~~~
혹시라도 또 생성해주는걸 막기위해서 init의 __접근 제어자__ 를 private로 지정해준다.  

# Singleton Class 접근하는 방법
만든 static 프로퍼티를 사용하면 된다.  
~~~
//AVC
let userInfo = UserInfo.shared
userInfo.id = "Sodeul"
~~~
~~~
//BVC
let userInfo = UserInfo.shared
userInfo.password = "123"
~~~
~~~
//CVC
let userInfo = UserInfo.shared
userInfo.name = "Sodeul"
~~~
이런식으로 만들면 이전 처럼 객체가 여러개 생기는게 아니라  
객체가 하나만 생성되고 공유할수 있게 되는 것이다.  
싱글톤 패턴 끝!!