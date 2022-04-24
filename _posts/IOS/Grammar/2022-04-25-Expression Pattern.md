---
title: Expression Pattern

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Expression Pattern

~~~
let a = 1

switch a{
  case 0...10:
    print("0~10")
  default:
    break
}
~~~
실행

~~~
0~10
~~~

# Pattern Matching Operator

~~~
struct Size {
  var width = 0.0
  var height = 0.0
}

let s = Size(width: 10, height: 20)

switch s {
  case 1..<9:
    print("1~9")
  case 10..<99:
    print("10~99")
  default:
    break
}
~~~
오류가 발생한다 매칭이 안되기 떄문에 따라서, 코드를

~~~
struct Size {
  var width = 0.0
  var height = 0.0

  static func ~=(left: Range<Int>, right: Size) -> Bool {
    return left.contains(Int(right.width))
  }
}

let s = Size(width: 10, height: 20)

switch s {
  case 1..<9:
    print("1~9")
  case 10..<99:
    print("10~99")
  default:
    break
}
~~~
