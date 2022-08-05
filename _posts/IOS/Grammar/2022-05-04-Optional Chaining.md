---
title: Optional Chaining

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Optional Chaining

Contacts구조체는 이메일과 주소를 저장하고, Person구조체는 이름과 주소정보를 저장한다.  
그리고 안에서 초기화를 시켜준다.  
~~~
struct Contacts {
  var email: [String: String]
  var address: String
}

struct Person {
  var name: String
  var contacts: Contacts

  init(name: String, email: String) {
    self.name = name
    contacts = Contacts(eamil.: ["home": email], address: "Seoul")
  }
}

var p = Person(name: "James", email: "swift@example.com")
let a = p.contacts.address

var optionalP: Person? = Person(name: "James", email: "swift@example.com")
let b = optionalP.contacts.address // -> error발생
~~~
error가 발생하는 이유는 무엇일까?
~~~
let b = optionalP.contacts.address // -> error발생
~~~
이 코드를 보면, 언매핑을 해야한다. 따라서 
~~~
let b = optionalP?.contacts.address // -> error해결
~~~
이렇게 언매핑을 해줘야한다.

코드에 하나라도 Optional이 있으면 그 코드는 Optional타입이 되어버린다.   
