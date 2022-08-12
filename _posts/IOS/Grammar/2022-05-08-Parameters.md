---
title: Parameters

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Parameters

~~~
func add() -> Int {
  return 1 + 2
}
~~~
실제로는 이렇게 사용하면 의미가 없다
~~~
func add(a: Int, b: Int) -> Int {
  return a + b
}

add(a: 1, b: 2)
~~~
이렇게 사용해야한다.

~~~
func sayHello(to: String = "Stranger") {
  print("Hello, \(to)")
}

sayHello(to: "Swift")
~~~
출력
~~~
Hello, Swift
~~~
하지만 파라미터를 생략하면
~~~
Hello, Stranger 
~~~
가 출력이 된다.  
파라미터를 넣지 않았기 때문에 기본으로 지정한 Stranger가 나오기 때문이다.