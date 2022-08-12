---
title: "CustomStringConvertible 프로토콜"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## CustomStringConvertible 프로토콜   

~~~ 
// CustomStringConvertible을 통해
// enum이나 struct, class 객체 등의 설명 변경이 가능하다.
enum Fruit: CustomStringConvertible {
    case apple
    case melon
    // 디스크립션 정의
    var description: String {
        switch self {
        case .apple: return "맛있는 꿀 사과가 왔어요~"
        case .melon: return "맛있는 멜론이 왔어요~"
        default: return "알 수 없음"
        }
    }
}
struct Pet: CustomStringConvertible {
    var name: String
    var description: String { return "우리집 강아지 \(name)"}
}

// 이처럼 프린트시 디스크립션으로 설정한 내용이 찍힙니다.
let myFruit = Fruit.apple
print("myFruit :", myFruit)
let myDog: Pet = .init(name: "똘똘이")
print("myDog: ", myDog)
~~~  

출력  
~~~
myFruit : 맛있는 꿀 사과가 왔어요~
myDog:  우리집 강아지 똘똘이
~~~  