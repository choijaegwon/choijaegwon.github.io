---
title: "Genserics"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Genserics

우선 이런 함수가 있다고하자
~~~
func swapInteger(lhs: inout Int, rhs: inout Int) {
  let tmp = lhs
  lhs = rhs
  rhs = tmp
}
~~~
메개변수 2개를 담고, 먼저 하나를 받고, tmp에 담아준후, rhs를 받고 lhs로, 사디 tmp에받은 값을 rhs로 담아주는 함수이다.
이런 교수하는 함수는 Int형만 담을 수있다.
만약 이러한 함수가 되게 많다면?
~~~
func swapInteger16(lhs: inout Int16, rhs: inout Int16) {
  let tmp = lhs
  lhs = rhs
  rhs = tmp
}

func swapInteger64(lhs: inout Int64, rhs: inout Int64) {
  let tmp = lhs
  lhs = rhs
  rhs = tmp
}
~~~
함수의 타입만 다르고, 형태는 아예 똑같다. 하지만 매번 이렇게 작성을 하면 코드가 너무 길어지는 단점이있다.  
또 값을 바꿔야한다면, 하나하나 고쳐서 바꿔줘야한다.  
이럴 필요가 없이 나온게 제네릭이다.  

# 문법
~~~
func name<T> (parameters) -> Type {
  code
}
~~~

사용해보면
~~~
func swapValue<T>(lhs: inout T, rhs, inout T) {
  let tmp = lhs
  lhs = rhs
  rhs = tmp
}
~~~
이러면 형식에 상관없이 모든 값을 호출할 수 있다.
