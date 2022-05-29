---
title: String Searching

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# String Searching
- 문자열을 검색하는 방법

~~~
let str = "Hello, Swift"

str.contains("Swift") // true 파라미터로 전달한 문자열이 있다면 true를 리턴함

str.lowercased().contains("swift") // true lowercased를 사용해서 대소문자구문이 없어짐.

let str2 = "Hello, Programming" // "Hello, Programming"
let str3 = str2.lowercased() // "hello, programming"

var common = str.commonPrefix(with: str2) // "Hello,"
~~~
이런 방식으로 공통된 부분을 따로 빼내어서 검색할 수 있다.