---
title: "Properties"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
  - Properties
---

## stored property(저장)
~~~
class MyInfo {

  // stored property(저장)
  var name = ""
  var age = 0
}

let myInfo = MyInfo()

myInfo.age = 10
myInfo.name = "kim"

print(myInfo.age)
~~~
출력하면
~~~
10
~~~
안에 들어있는 name, age같은게 Properties다.
## lazy stored property
만약에 위 코드에서
~~~
class MyInfo {

  // lazy stored property
  var myProfiles = [UIImage(named: "n"), UIImage(named: "c"), UIImage(named: "w"),
                    UIImage(named: "d"), UIImage(named: "a"),]

}
~~~
var myProfiles 이부분을 추가를 시키면, 클래스가 인스턴스화 되는 시점에  
과부하가 많이 걸릴수 있다.(UIImage가 많이 있기 때문)  
하지만 바로 필요한 이미지가아니고, 나중에 버튼을 눌렀을떄 사용하는 이미지면,  
앞에다가 lazy 를 붙이면 된다.
~~~
  // lazy stored property
  lazy var myProfiles = [UIImage(named: "n"), UIImage(named: "c"), UIImage(named: "w"),
                    UIImage(named: "d"), UIImage(named: "a"),]
~~~
lazy는 사용하려고 할때 또는 접근하려고할때 그때 올라가는 property다.

## computed property(계산)
특정한 값에 의해서 결정되는 값이 있다.  
예를들어 성인이냐 등등
~~~
class MyInfo {
  
  // computed property(계산)
  var isAdult: Bool {
    if age > 19 {
      return true
    }
    return false
  }

}
~~~
이렇게 정해 놓으면 된다. 그러면 자동으로 나이를 입력했을때 성인인지 아닌지를 판별할수 있다.  

다른 예시를 보면,  

~~~
class MyInfo {
  
  // computed property(계산)
  // email -> 보안 -> 암호화 된 값으로 사용한다.(항상)
  var _email = "" //안에서사용할 변수
  var email: String {
    get{
      return _email
    }
    set{
      _eamil = newValue.hash.description
    }
  }

}

ley muInfo = MyInfo()
myInfo.email = "abc@text.com"
~~~
hash값을 암호화 하는 로직이라고 치고 실행하면 이메일이 바뀌는걸 확인할 수있다.
~~~
"21812902490120"
~~~
set은 다른 Properties에 값을 저장할때 사용하고(설정하는것)  
get은 다른 Properties에 값을 얻거나 연산하여 리턴할때 사용한다.(항상 return구문이 존재)