---
title: Substring 

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Substring  
- 문자열을 사용할때 메모리를 절약하기위해서
- 원본문자의 메모리를 공유한다.

~~~
let str = "Hello, Swift" // "Hello, Swift"
let l = str.lowercased() // "hello, swift"
 
var first = str.prefix(1) // H -> 메모리를 공유한다. -> 원본을 사용한다.

first.insert("!", at: first.endIndex) // 이시점에 새로운 메모리가 생긴다

str // "Hello, Swift"
first // "H!" 

let newStr = String(str.prefix(1)) // Substring을 생성자로 바로 전달하면 새로운 메모리가 생성된다.
~~~

