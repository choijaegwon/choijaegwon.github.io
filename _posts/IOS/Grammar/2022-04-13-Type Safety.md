---
title: Type Safety

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

~~~
let rate = 1.94
let amt = 10_000_000
let result = rate * amt
~~~
오류가 나타낸다. 그이유는 타입이 다르기 때문이다.  
rate는 double amt는 int 이기 때문이다.  

따라서, amt를 Double형으로 바꿔주면 계산이 가능해진다.  

~~~
let rate = 1.94
let amt = 10_000_000
let result = rate * Double(amt)
~~~

출력
~~~
19400000
~~~
