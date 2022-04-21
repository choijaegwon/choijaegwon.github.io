---
title: switch Statement

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# switch

- 꼭 default값이 있어야한다 (break라도)
- 다양한 값을 쓰고 싶으면 , 로 추가해주면 된다.
~~~
let num = 1

switch num {
  case 1:
    print("one")
  case 2, 3:
    print("two or three")
  default:
    print("others")
}
~~~
  

# 패턴에 조건 추가하기
- where를 사용해서 조건을 추가할 수 있다.

~~~
let num = 1

switch num {
  case let n where n <= 10:
    print(n)
  default:
    print("others")
}
~~~

# Interval Matching

~~~
let temperature = -8

switch temperature {
  case ..<10:
    print("Cold")
  case 10...20:
    print("Cool")
  case 20...27:
    print("Warm")
  case 27...:
    print("Hot")
  default:
    break
}
~~~
실행
~~~
Cold
~~~

# Fall Through

~~~
let num = 2

switch num {
  case 1:
    print("one")
  case 2:
    print("two")
  case 3:
    print("three")
  default:
    break
}
~~~
출력
~~~
two
~~~

위 코드에서 fallthrough를 실행하면,  
~~~
let num = 2

switch num {
  case 1:
    print("one")
  case 2:
    print("two")
    fallthrough
  case 3:
    print("three")
  default:
    break
}
~~~
출력
~~~
two
three
~~~
값이 나온다.  
- fallthrough를 실행하면 다음 코드를 실행한다.

