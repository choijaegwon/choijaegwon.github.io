---
title: Instance Method
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Instance Method
- 클래스, 구조체, 열거형에서 사용이가능하다.  
- 인스턴스마다 실행결과가 달라진다.

~~~
class Sample {
  var date = 0
  static var sharedData = 123

  func doSomething() {
    print(data)
    Sample.sharedData
  }

  func call() {
      doSomething()
  }
}

let a = Sample()
a.data
a.doSomething()
a.call()
~~~
이렇게 Sample이라는 class틀을 이용해 a라는 인스턴스를 생성한후,  
a를 이용해 class내부에 만든 변수와 함수에 접근할 수 있다.
