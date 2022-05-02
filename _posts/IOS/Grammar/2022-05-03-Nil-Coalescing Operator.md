---
title: Nil-Coalescing Operator

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Nil-Coalescing Operator

~~~
var msg = ""
var input: String? = "Swift"

if let inputName = input {
  msg = "Hello, " + inputName
} else {
  msg = "Hello, Stranger"
}

print(msg) // "Hello,Swift"
~~~
조건 연산자를 사용해서 좀 더 단순하게 구현해보면,
~~~
var msg = ""
var input: String? = "Swift"

var str = "Hello, " + (input != nil ? input! : "Stranger")
print(str)
~~~
input값이 있으면 "Swift"를 출력하고 없으면 "Stranger"를 출력하게되지만, 너무 복잡해 보인다. 
하지만 Nil-Coalescing Operator를 사용하면 쉽게 사용이 가능하다
~~~
var input: String? = "Swift"

str = "Hello, " + (input ?? "Stranger")
print(str)
~~~
input에 값이 있는지 확인한다. 값이 있으면 언매핑하고 그값을 주고, 
값이 없으면 "Stranger"이 나온다.