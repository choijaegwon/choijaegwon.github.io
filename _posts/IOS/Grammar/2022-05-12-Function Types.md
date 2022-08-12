---
title: Function Types

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Function Types
- 변수나 상수에 저장할 수 있다.
- 파라미터로 전달할 수 있다.
- 함수에 저장할 수 있다.

# 형식추론
~~~
func sayHello() {
  print("Hello, Swift")
}

let f1 = sayHello //sayHello()라고하면 에러가 된다 함수가 호출되기 때문이다.
f1() // ()->() Hello,Swift
~~~

# 직접 자료형 선언
~~~
func printHello(with name: String) {
  print("hello, \(name)")
}

let f2: (String) -> () = printHello(with:) // (String) -> ()

let f3 = printHello(with:) // (String) -> ()
f3("World") // hello, World

func add(a: Int, b: Int) -> Int {
  return a + b
}

var f4: (Int, Int) -> Int = add(a:b:)

f4(1, 2) // 3

func add(_ a: Int, with b: Int) -> Int {
  return a + b
}
f4 = add(_:with:)

func swapNumbers(_ a: inout Int, _ b: inout Int) {

}

let f5 = swapNumbers(_:_:)
f5 // (inout Int, inout Int) -> () 

func sum(of numbers: Int...) {

}

let f6 = sum(of:)
f6 // (Int...) -> ()
~~~

# 사칙연산 코드

~~~
func add(_ a: Int, _ b: Int) -> Int {
  return a + b
}

func subtract(_ a: Int, _ b: Int) -> Int {
  return a - b
}

func multiply(_ a: Int, _ b: Int) -> Int {
  return a * b
}

func divide(_ a: Int, _ b: Int) -> Int {
  return a / b
}

typealias ArithmeticFunction = (Int, Int) -> Int

func selectFunction(from op: String) -> ArithmeticFunction? {
  switch op {
    case "+":
      return add(_:_:)
    case "*":
      return multiply(_:_:)
    case "-":
      return subtract(_:_:)
    case "/":
      return divide(_:_:)
    default:
      return nil
  }
}

let af = selectFunction(form: "+") //(Int, Int) -> Int
af?(1, 2) //출력 3

selectFuncton(form: "*")?(12, 34) // 408
~~~


