---
title: Nested Functions

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Nested Functions
- 내포된 함수 
- 다른함수에 포함되어 있는 함수

그냥 함수
~~~
func outer() {
  print("outer")
}

func inner() {
  print("inner")
}

outer() // outer
inner() // inner
~~~
이렇게 따로따로 그냥 사용할 수 있다. 하지만,  

~~~
func outer() {
  func inner() {
    print("inner")
  }

  print("outer")
}
~~~
이렇게 사용하면 Nested Function이 된다. 이렇게 되면
글로벌스코프에서 inner함수를 호출할수 없게 된다.  

~~~
func outer() -> () -> () {
  func inner() {
    print("inner")
  }

  print("outer")

  return inner
}

let f = outer() // () -> ()
f() // () -> ()
~~~
이렇게 사용하면(리턴하면) inner함수를 사용할 수 있게 된다.