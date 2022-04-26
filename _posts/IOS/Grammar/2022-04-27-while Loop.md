---
title: while Loop

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# while
- true면 진행, false면 중단

~~~
var num = 1
var sum = 0 

while num <= 100 {
  sum += num
}

sum
~~~
이렇게 하면 무한루프에 빠진다. 왜? 항상 num이 1이기때문에  
고치려면,

~~~
var num = 1
var sum = 0 

while num <= 100 {
  sum += num
  num += 1
}

sum
~~~
이렇게 num이라는 변수를 1씩 증가시키면 된다.

# repeat-while
- 코드를 먼저 실행한 후, 조건을 판단

~~~
var num = 100
while num < 100 {
  num += 1
}
num
~~~
위와 아래 둘 코드를 비교,
~~~
num = 100
repeat {
  num += 1
} while num < 100

num
~~~
위에는 100, 아래는 101이 나온다. 그 이유는,  
위 코드는 100이 바로 나와서 true가 되는것이고,  
아래 코드는 100이 여도 일단 코드를 실행부터 하기 때문에, 101이 되는 것이다.