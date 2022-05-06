---
title: Return Values

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Return Values

~~~
func add() -> Int {
  return 1 + 2
}

add()
~~~
출력
~~~
3
~~~
이렇게 사용도 가능하다
~~~
let r = add() // r값엔 3이 저장되어있다.

if add() == 3 {
  print("three")
}
~~~
출력해보면
~~~
three
~~~
가 출력이된다.

## 숫자를 랜덤으로 생성하고 짝수면 출력을하고 홀수면 종료하는 함수

~~~
func doSometing() {
  let rnd = Int.random(in: 1...10)

  if rnd % 2 == 1{
    return
  }

  print(rnd)
}
~~~

