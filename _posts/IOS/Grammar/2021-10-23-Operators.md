---
title: "Operators"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
  - Operators
---

## Operators(기초연산자)
## +
- 같은 형태만 더할수 있다.
- Int + Int 이런 형식만 가능하다.  

~~~
let a = 20
let b = 30
let c = a + b
~~~
~~~
50
~~~  
## -
~~~
let a = 20
let b = 30
let c = a - b
~~~
~~~
-10
~~~
## *
~~~
let a = 20
let b = 30
let c = a * b
~~~
~~~
600
~~~
## / 
~~~
let a = 20
let b = 30
let c = a / b
~~~
~~~
0
~~~
Int타입 이기 때문에 0 이 나온다.  
## % 홀수 짝수
~~~
let a = 20
if a % 2 == 0 {
  print("짝수")
} else{
  print("홀수")
}
~~~
~~~
짝수
~~~
Double형태일땐  
__.truncatingRemainder(dividingBy: 값)__ 이런방식으로 사용하면 된다.  
ex)  
~~~
let b:Double = 30
if b..truncatingRemainder(dividingBy: 2) == 0 {
  print("짝수")
} else{
  print("홀수")
}
~~~
~~~
짝수
~~~  
---  

~~~
let a = 20
let b = 20

a == b 
~~~
~~~
true //Bool타입
~~~