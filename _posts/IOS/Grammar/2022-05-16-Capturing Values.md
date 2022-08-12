---
title: Capturing Values

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Capturing Values  
- 값을 Capturing하여 복사본을 가져오는 방법(Object-c)
- 참조를 Catruing하여 원본을 가져오는 방법(Swift)


~~~
var num = 0 
let c = { print("check point #1: \(num)") }
c()

num += 1
print("check point #2: \(num)")
~~~
를 출력하면
~~~
check point #1: 0 
check point #2: 1
~~~
인데 
~~~
var num = 0 
let c = { 
  num += 1
  print("check point #1: \(num)") 
}
c()

print("check point #2: \(num)")
~~~
이렇게 클로져 안에서 Capturing을 한 값을 보면
~~~
check point #1: 1 
check point #2: 1
~~~
이렇게 참조한 값(원본)이 바뀐다.
