---
title: String Comparison

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# String Comparison  

~~~
let largeA = "Apple" // "Apple"
let smallA = "apple" // "apple"
let b = "Banana" // "Banana"

largeA == smallA // false
largeA != smallA // true

largeA < smallA // true
largeA < b // true
smallA < b // false

largeA.compare(smallA) == .orderedSame // false
largeA.caseInsensitiveCompare(smallA) // true
~~~
이런식으로 문자열을 비교할 수 있다.  
~~~
let str = "Hello, Swift Programming!" // "Hello, Swift Programming!"
let prefix = "Hello" // "Hello"
let suffix = "Programming" // "Programming"

str.hasPrefix(prefix) // true 앞부분이 동일하기 떄문에

str.hasSuffix(suffix) // false 뒤에 !가 포함되어 있어서 둘이 달라서 false
~~~
hasPrefix나hasSuffix는 대소문자도 비교한다.