---
title: break Statement

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# break
- break는 함수를 문장을 종료하고 제어를 이어지는 코드로 이동시킨다.
- 문장이 중첩되어있을때 가장 가까운 제어문만 제어한다.

~~~
let num = 1

switch num {
  case 1...10:
    print("begin block")

    if num % 2 != 0 {
      break
    }

    print("end block")
default:
  break
}

print("done")
~~~
출력
~~~
begin block
done
~~~

# 반복문안에서 
~~~
for index in 1...10 {
  print(index)

  if index > 1 {
    break
  }
}
~~~
출력
~~~
1
2
~~~
break를 만나 종료된다.
