---
title: "repeat while 반복문"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## repeat while 반복문  

~~~
var count = 6
let max = 5
// 반복한다. 일단 실행함
// 다른언어의 do while과 비슷
repeat {
    count = count + 1
    print("count: ", count)
} while count < max // 5보다 작을때 까지
print("\(count) 까지 셌다")
// count: 7
// 7 까지 셌다

// while 문에서는 조건을 먼저보고
// 들어가기 때문에 로직을 안탑니다.
while count < max {
    count = count + 1
    print("count: ", count)
}
~~~  

출력  
~~~
count:  7
7 까지 셌다
~~~  