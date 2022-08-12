---
title: Enumeration Case Pattern

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Enumeration Types

## Enumeration Case Pattern

~~~
enum Transportation {
  case bus(number: Int)
  case taxi(company: String, number: String)
  case subway(lineNumber: Int, express: Bool)
}

var tpt = Transportation.bus(number: 7)

switch tpt {
  case .bus(let n):
    print(n)
  case .taxi(let c, var n):
    print(c, n)
  case let .subway(l, e):
    print(l, e)
}

tpt = Transportation.subway(lineNumber: 2, express: false)

// 2호선만 확인하고싶을 떄
if case let .subway(2, express) = tpt {
  if express {

  } else {

  }
}

// 급행지하철만 확인하고싶을 떄
if case .subway(_, true) = tpt {
  print("express")
}
~~~
이런방식으로 enum타입을 활용해서 조건문과 반복문에서 연관 값을 매칭 시킬 수 있다.