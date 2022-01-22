---
title: "중첩 타입(nested type)"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## 중첩 타입(nested type)  

~~~
struct MyPet {
    enum Kind { // 스트럭트안에 enum 타입
        case cat // kind enum의 케이스
        case dog
        // enum은 value와 name 이라는 변수를 가지고
        var value: String {
            switch self { // 자신의 타입에 따라 값이 부여
            case .cat:
                return "고양이"
            case .dog:
                return "강아지"
            }
        }
        var name: String {
            switch self {
            case .cat:
                return "개냥이"
            case .dog:
                return "해피"
            }
        }
    }
    let kind: Kind // MyPet 스트럭트가 가지는 Kind 변수
    var description: String { // 값 확인을 위한 변수
        return "우리집 \(kind.value) '\(kind.name)'에요"
    }
}

let myCat = MyPet(kind: .cat)
print(myCat.description) // 우리집 고양이 '개냥이'에요

let myDog = MyPet(kind: .dog)
print(myDog.description) // 우리집 강아지 '해피'에요
~~~  

출력  
~~~
우리집 고양이 '개냥이'에요
우리집 강아지 '해피'에요
~~~  