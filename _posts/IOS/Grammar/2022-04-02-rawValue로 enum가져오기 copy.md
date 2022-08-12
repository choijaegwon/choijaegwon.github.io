---
title: "rawValue로 enum가져오기"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## rawValue로 enum가져오기   

~~~ 
enum PetType: String { // 애완동물 enum type
    case dog = "강아지"
    case cat = "고양이"
    case none
    // Enum에 생성자들 두어 rawValue로 이넘타입을 가져올 수 있다.
    init(value: String) {
        switch value {
        case "강아지": self = .dog
        case "고양이": self = .cat
        default: self = .none
        }
    }
}

//RawValue로 이넘 생성!
let petType = PetType(rawValue: "강아지")
switch petType {
case .dog:
    print("강아지 입니다")
case .cat:
    print("고양이 입니다")
default:
    print("알수없음") 
}
~~~  

