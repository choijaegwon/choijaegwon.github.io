---
title: "enum타입에서 Caselterable프로토콜"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## enum타입에서 Caselterable프로토콜  
- CaseIterable 프로토콜을 통해 이넘 타입도 콜렉션처럼 사용이 가능하다.  

~~~
enum Pet: String, CaseIterable {
    case cat = "고양이"
    case dog = "강아지"
    case trueBird = "참새"
}

//allCases를 통해
// 이넘의 타입들을 콜렉션으로 가져옵니다.
let petKindsCount = Pet.allCases.count
print("애완동물 종류수: \(petKindsCount)")
~~~  

출력  
~~~
애완동물 종류수: 3
~~~  

반복문도 가능하다  

~~~
for petTypeItem in Pet.allCases {
    print(petTypeItem.rawValue)
}
~~~  

출력
~~~
고양이
강아지
참새
~~~ 