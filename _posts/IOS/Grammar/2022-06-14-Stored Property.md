---
title: Stored Property
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Stored Property  
- 저장 속성
- 클래스와 구조체에서 선언할 수 있다.
- 형식추론을 통해서 생략이 가능하다.
- var는 바꿀 수있고 let은 바꿀 수 없다.

~~~
class Person {
  let name: String = "John Doe"
  var age: Int = 33
}
~~~
name은 let으로 설정되어 있어서 바꿀 수 없지만,  
age는 var로 설정되어 있어서 바꿀 수 있다.
name과 age가 저장 속성이다.  

~~~
let p = Person()
p.name
p.age
p.age = 30 //에러
p.name = "New Name" //에러
~~~
이렇게 인스턴스를 바꾸려면 에러가 발생한다.  
인스턴스를 생성할 때 let으로 만들었기 때문이다.