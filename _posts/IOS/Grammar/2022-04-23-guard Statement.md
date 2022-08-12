---
title: guard Statement

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# guard
- guard문에는 else블록을 생략할 수 없다.
- 중첩을 피할 수 있다.

~~~
func validate(id: String?) -> Bool {
  guard let id = id else {
    return false
  }

  guard id.count >= 6 else {
    return false
  }

  return true
}

validate(id: nil) // false

validate(id: "abc") // false

validate(id: "swiftlang") //true
~~~

## guard문과 if문의 코드차이

~~~
func validateUsingIf() {
  var id: String? = nil

  if let str = id {
    if str.count >= 6 {
      print(str)
    }
  }
}

func validateUsingGuard() {
  var id: String? = nil

  guard let str = id else { return }
  guard str.count >= 6 ele { return }

  print(str)
}
~~~

- if문은 조건을 추가할수록 코드가 중첩이 된다. 
- guard는 else문 이후에 사용이 가능하다.

보통, 조건이 하나이거나 조건 자체가 단순하면 If  
복잡하거나 여러단계로 중첩해야할때는 guard문을 사용하는게 좋다.