---
title: Dynamic Member Lookup
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Dynamic Member Lookup  
- 접문법으로 서브스크립트에 접근하는 단축문법을 구현하게 해준다.

~~~
@dynamicMemberLookup
struct Person {
  var name: String
  var address: String

  subscript(dynamicMember member: String) -> String {
    switch member {
      case "nameKey":
        return name
      case "addressKey":
        return address
      default:
        return "n/a"
    }
  }
}

let p = Person(name: "James", address: "seoul")
p.name
p.address

p[dynamicMember: "nameKey"]
p[dynamicMember: "addressKey"]

p.nameKey
p.addressKey
~~~