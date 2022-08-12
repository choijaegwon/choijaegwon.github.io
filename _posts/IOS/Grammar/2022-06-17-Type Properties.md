---
title: Type Properties
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Type Properties
- 형식 속성
- static을 사용한다
- 공유되는 변수라고 생각하면 된다.
- 형식의 이름을 통해서 접근해야한다.  

~~~
class Math {
  static let pi = 3.14
}

let m = Math()
Math.pi // 3.14 -> 이렇게 Class로 접근해야한다.
~~~
처음에 접근하는 시점에서 초기화 된다.  

