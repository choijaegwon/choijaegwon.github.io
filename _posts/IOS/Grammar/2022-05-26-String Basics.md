---
title: String Basics 

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# String Basics 

~~~
var str = "Hello, Swift String"
var emptyStr = ""
emptyStr = String()

let a = String(true) // "true"문자열 true
let b = String(12) // "12" 문자열 12
let c = String(12.34) // "12.34" 문자열 12.34

let hex = String(123, radix: 16) // "7b" 16 진수로 바꿈
let octal = String(123, radix: 8) // "173" 8진수로 바꿈
let binary = String(123, radix: 2) // "1111011" 2진수로 바꿈

let repeatStr = String(repeating: "z", count: 7) // zzzzzzz 이렇게 사용이 가능하다.

let e = "\(a) \(b)" // true 12
let f = a + " " + b // true 12

str.count // 문자열의 개수 확인가능.
str.isEmpty //빈문자열이면 true 아니면 false

//  ed와 ing로 끝나면 원본은 두고 값을 복제해 사용한다.
str.lowercased() // "hello, swift string"
str.uppercased() // "HELLO, SWIFT STRING"
str.capitalized // "Hello, Swift String" 첫문자만 대문자로 만들어준다.
~~~