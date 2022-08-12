---
title: "(getter, setter)"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## (getter, setter)  

~~~
// 친구 클래스
class Friend {
    var name : String = ""
    //nikname 게터와 세터 설정을 통해
    // 해당 멤버 변수 데이터를 가져올때
    // 해당 멤버 변수에 값을 설정할때 로직을 추가할 수 있다.
    var nickname : String {
        get {
            return "내 친구: " + name
        }
        set {
            name = newValue + " (내가 지어준 별명)"
        }
    }
}

let myFriend = Friend()
myFriend.name = "철수"
print(myFriend.nickname)
// 내 친구: 철수

myFriend.nickname = "빡빡이"
print(myFriend.nickname)
~~~  

출력  
~~~
내 친구: 철수
내 친구: 빡빡이 (내가 지어준 별명)
~~~  