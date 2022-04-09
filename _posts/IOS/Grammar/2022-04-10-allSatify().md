---
title: "allSatify()"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## allSatify()   

~~~ 
let names = ["철수", "영희", "존슨"]
// allSatisfy를 통해 콜렉션 안 요소들이
// 모두 같은 조건에 부합하는지 확인이 가능합니다.
var nameCountAtLeastTwo = names.allSatisfy { (name: String) -> Bool in name.count <= 2}

print("nameCountAtLeastTwo:", nameCountAtLeastTwo)
// nameCountAtLeastTwo == true

let foreignNames = ["제시", "제임스", "맥"]

nameCountAtLeastTwo = foreignNames.allSatisfy({ $0.count <= 2})
print("nameCountAtLeastTwo:" , nameCountAtLeastTwo)
// nameCountAtLeastTwo == false
~~~  

