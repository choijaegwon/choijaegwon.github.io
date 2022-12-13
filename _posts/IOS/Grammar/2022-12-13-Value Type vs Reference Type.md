---
title: Value Type vs Reference Type
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Value Type vs Reference Type
- 값타입은 스택에 저장되어 인스턴스를 찍을때 값이 복사가 된다
- 참조타입은 스택에 힙의메모리주소를 저장하고 힙의 메모리주소를 가르켜 인스턴스를 찍을때 값이 참조가 된다.

~~~
struct SizeVaule {
  var width = 0.0
  var height = 0.0
}

var value = SizeValue()
var value2 = value // 값이 복사됨
value2.width = 1.0
value2.height = 2.0

//값을 복사했기 때문에 value값은 그대로임
value // 0.0 0.0
value2 // 1.0 2.0


class SizeObject {
  var width = 0.0
  var height = 0.0
}

var object = SizeObject()
var object2 = object // 값의 주소가 그대로 복사됨 

object2.width = 1.0
object2.height = 2.0 

// 값의 주소를 둘다 가르키기 때문에 object의 값이 둘다 바뀜
object // 1 2
object2 // 1 2
~~~