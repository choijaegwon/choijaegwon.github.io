---
title: Optional Binding

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Optional Binding
- 안전하고 직관적이게 코드할수 있다.
- if let, while let, guard let 등을 사용한다.

# if let

~~~
var num: Int? = nil

if num != nil {
  print(num!)
} else {
  print("empty")
}
~~~
를
~~~
var num: Int? = nil

if let n = num {
  print(n)
} else {
  print("empty")
}
~~~ 
로 바꿀 수 있다.

## 바인딩 두번도 가능하다

~~~
let a: Int? = 12
let b: String? = "str"

if let num = a, let str = b, str.count > 5 {
  //조건이 다 만족하면 이 안에있는 코드가 실행이 된다.
}
~~~