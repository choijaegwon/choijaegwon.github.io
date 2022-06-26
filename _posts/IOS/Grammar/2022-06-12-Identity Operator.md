---
title: Identity Operator
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Identity Operator  
- 항등 연산자
- 메모리주소를 비교할 때 사용
- 인스턴스의 주소가 동일한 경우 ture를 return 한다.  

~~~
class A {

}

let a = A()
let b = a
let c = A()

a === b //true
~~~
동일한 메모리 주소가 저장되어 있기 때문에 true를 return해준다.

~~~
a !== c //true
~~~
서로 다른 인스턴스가 저장되어 있기 때문에 true가 return된다.
