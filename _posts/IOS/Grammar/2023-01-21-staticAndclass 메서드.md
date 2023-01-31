---
title: "staticAndclass 메서드"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# staticAndclass 메서드
이전 싱글톤 패턴글을 작성하면서 오랜만에 static메서드를 보았다.  
분명 완벽하게 알고있었는데 뭐지..? 갑자기 기억이 안난다...  
따라서 이번 기회에 다시한번 정리해 보려고 한다.  

# 인스턴스 메서드
우선, 우리가 알아야할건 "인스턴스 메서드" 이다.  
인스턴스 메서드란?  
우리가 평소에 사용하고있는 모든 것들이 다 "인스턴스 메서드"였다.  
~~~
class Dog {
  func doSomething() {
    print("잠자기")
  }
}
~~~
## 인스턴스 메서드를 호출방법
~~~
let popo: Dog = .init()
popo.doSomething()
~~~
이런 방식으로 popo라는 인스턴스를 생성하고, 거기에 . 을 사용하여서   
메서드에 접근하는 우리가 평소에 사용하는 방식이다.  

# 타입 메서드  
~~~
class Dog {
  static func oneBarking() {
    print("멍")
  }
  class func twoBarking() {
    print("멍멍")
  }
}
~~~
이런식으로, func 앞에 static 또는, class가 붙은게 모두 타입 메서드 이다.  

## 타입 메서드의 호출방법
~~~
Dog.oneBarking()
Dog.twoBarking()
~~~
인스턴스를 생성하지않고, 그냥 바로 Type(여기선 Dog)을 적어주면 된다.  

## 궁금증
그러면 class, static둘다 타입메서드인데 언제 class, 언제 static사용할까?  
이 둘의 차이점은 메서드 오버라이딩의 여부이다.  
메서드를 재정의하는게 가능한것이 class,  
불가능하는 것이 static이다.  
