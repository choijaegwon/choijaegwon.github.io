---
title: Any, AnyObject
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Any, AnyObject
- 범용 자료형이다.
- Any: 모든형식을 저장할 수 있다.
- AnyObject: 모든 클래식 형식을 저장할 수 있다.

~~~
var data: Any = 1
data = 2.3
data = "str"
data = [1, 2, 3]
data = NSString()
~~~
이렇게 모든 자료형이 저장이 가능하다. 하지만, 추후 유지보수를 하기 어렵다.  

~~~
if let str = data as? String {
  print(str.count)
}
~~~
사용하려면 이렇게 사용해야 한다. 


## Type Casting Pattern
활용해보면
~~~
switch data {
  case let str as String:
    print(str.count)
  case let list as [Int]:
    print(list.count)
  case is Double:
    print("Double Value")
  default:
    break
}
~~~
이런식으로 활용할 수 있다.