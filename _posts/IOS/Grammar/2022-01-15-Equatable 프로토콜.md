---
title: "Equatable 프로토콜"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## Equatable 프로토콜  

~~~
struct PetKind {
    let name: String
}

struct Pet {
    let id: String
    let name: String
    let kind: PetKind
}
// Equatable 프로토콜을 통해서 커스텀 비교 연산자를 만들수 있다.
extension Pet: Equatable {
    public static func == (lhs: Pet, rhs: Pet) -> Bool {
        return lhs.id == rhs.id && lhs.kind.name == rhs.kind.name
    }
}

let catKind = PetKind(name: "고양이")
let dogkind = PetKind(name: "강아지")
let myPet1 = Pet(id: "01", name: "개냥이", kind: catKind)
let myPet3 = Pet(id: "01", name: "댕댕이", kind: dogkind)
let myPet4 = Pet(id: "01", name: "개냥이", kind: catKind)

if myPet1.id == myPet3.id && myPet1.kind.name == myPet3.kind.name {
    print("두 팻이 같다")
} else {
    print("두 팻이 다르다")
}
// 커스텀 비교 연산자
print(myPet1 == myPet4)
~~~  

출력  
~~~
true
~~~  