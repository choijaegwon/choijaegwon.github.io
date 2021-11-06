---
title: "기본 문법(Inheritance)"

categories:
  - UIkit
tags:
  - IOS
  - Swift
  - Inheritance
---

## Inheritance(상속)
- 상속
- 클래스에서만 가능하다.

~~~
class UserInfo {
  var name = ""
  var age = 0
  func isAdult() -> Bool {
    if age > 19 {
      return true
    }
    return false
  }
}
class Guest: UserInfo {
  override func isAdult() -> Bool {
    return true
  }
}
~~~
class를 상속 받는 Guest는 class에 있는걸 다 가져다 쓰는 것이다.  
하지만 이렇게 override를 쓰면 위 클래스인UserInfo에 구현되어 있는 걸 재정의한다는 뜻이다.  
super를 통해서 부모클래스에 접근할 수 있다.
~~~
class UserInfo {
  var name = ""
  var age = 0
  func isAdult() -> Bool {
    if age > 19 {
      return true
    }
    return false
  }
}
class Guest: UserInfo {
  override func isAdult() -> Bool {
    return true
  }
  func present() {
    name = "kim"
    print(name)
    print(super.name)
  }

}
let guest = Guest()
guest.present()
~~~
출력해보면
~~~
kim
kim
~~~
이렇게 되는데 그이유는 밑에 present는 부모에있는 name를 사용하기 때문이다.  
다르게 사용해보면,  
~~~
class UserInfo {
  var name = ""
  var age = 0
  func isAdult() -> Bool {
    if age > 19 {
      return true
    }
    return false
  }
}
class Guest: UserInfo {
  override func isAdult() -> Bool {
    return true
  }
  func present() {
    name = "kim"
    print(name)
    print(super.name)

    //추가된 부분
    print(isAdult())
    print(super.isAdult())
  }

}
let guest = Guest()
guest.present()
~~~
를 보면 isAdult()가 가르키는건 같은 메서드안에true라고 적혀있는(override된) 메서드를 가르키고있고,  
super.isAdult()는 위 UserInfo안에 있는 isAdult()를 가르키고 있는 것이다.