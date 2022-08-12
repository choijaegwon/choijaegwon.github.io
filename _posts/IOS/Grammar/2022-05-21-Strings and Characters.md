---
title: Strings and Characters

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Strings and Characters

문자열은
~~~
let s = "String"
let c = "C" 
~~~
둘다 문자열이다.

Character형으로 바꾸고 싶으면,
~~~
let c: Character = "C"
~~~
로 이렇게 바꿔야한다.

~~~
let emptychar: Character = " "

let emptyString = ""
~~~
이렇게 써야지 빈 문자열로 사용이 가능하다.

## Mutability
- 가변성

~~~
let immutableStr = "str"
immutableStr = "new str" //error발생

var mutableStr = "str"
mutableStr = "new str" //가능하다
~~~

## Unicode

~~~
let str = "Swift String"

str.utf8 //특정 인코딩으로 가능하다.
str.utf16 //특정 인코딩으로 가능하다.
~~~