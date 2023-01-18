---
title: "싱글톤 패턴(Singleton Pattern)"

categories:
  - IOSUIkit
tags:
  - IOS
  - Swift
---

# 싱글톤 패턴(Singleton Pattern)
- 객체를 하나만 사용하여, 공용으로 사용하고 싶을 때 사용하는 디자인 유형
- 보통 네트워크 통신을 할때 많이 사용이 된다.  

# 예제
쉽게 예제로 설명을 하자면  
~~~
class UserInfo {
  var id: String?
  var password: String?
  var name: String?
}
~~~
AVC에서 id, BVC에선 password, CVC에선 name을 입력받아서
UserInfo라는 클래스에 저장을 해야한다면  
~~~
//AVC
let userInfo = UserInfo()
userInfo.id = "Sodeul"
~~~

~~~
//BVC
let userInfo = UserInfo()
userInfo.password = "123"
~~~
~~~
//CVC
let userInfo = UserInfo()
userInfo.name = "Sodeul"
~~~
이런식으로 객체를 만들고 저장하고 만들고 저정하고 해야한다 근데 그러면  
각각의 속성에만 저장될 것이고 한곳에 모으질 못한다.(모으려고하면 되긴하는데 C->B->A) 이런식으로 화면을 내리면서 모으던가 해야한다. 이럴떄 사용하는것이 바로 싱글톤 패턴이다. 정리해 보면  
 "이 클래스에 대한 Instance는 최초 생성될 때 딱 한번만 생성해서 전역에 두고,
그 이후로는 이 Instance만 접근 가능하게 하자" 라는게 싱글톤 패턴이다.
어느 클래스에서든 접근가능하게 하는것이다.  
사용법은 다음 2탄에서 작성하겠다.  