---
title: Raw Strings

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Raw Strings 
- #" "#을 사용하면 그대로 나온다.

문자앞에 "를 붙이고 싶으면 \ 를 사용해야한다.
~~~
var str = "\" Hello \", Swift 5"

print("== str =====")
print(str)
~~~
출력해보면,
~~~
== str ====
"Hello", Swift 5
~~~
이렇게 말이다. 하지만 다른 방법이 있다.  

~~~
var rawStr = #"\"Hello\", Swift 5"#

print("== raw str =====")
print(rawStr)
~~~
출력해보면,
~~~
== raw str =====
\"Hello\", Swift 5
~~~
이렇게 나온다. 따라서 가독성을 높히려면,

~~~
var str = "\" Hello \", Swift 5"
var rawStr = #""Hello", Swift 5"#
~~~
이렇게 사용하면
~~~
"Hello", Swift 5
~~~
둘다 이렇게 나온다. 즉, #" "#을 사용하면 그대로 나온다.  
중간에 줄 바꿈을 하고싶으면 #n을 넣어주면 된다.