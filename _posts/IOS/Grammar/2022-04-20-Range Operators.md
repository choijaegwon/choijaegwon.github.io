---
title: Range Operators

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# 범위 연산자

## Closed Range Operator
- 이항연산자와 단항연산자로 사용된다.
- 단항 연산자로 사용될때는 피연산자와 붙여서 사용해야 한다.
~~~
a ... b
a...
...a
~~~

1에서부터 10까지 표현하는 방법
~~~
1 ... 10
~~~
10이 포함이 된다.  
하지만,  

10에서부터 1까지 표현하는 방법은
~~~
10 ... 1
~~~
에러가 표시가 난다. 그 이유는 upperBound는 lowerBound보다 작을수가 없기 때문이다.  
따라서, 내림차순으로 정리하고싶으면   

~~~
(1 ... 10).reversed()
~~~
reversed()메서드로 뒤집어 줘야한다.

## Half-Open Range Operator

- upperBound가 범위가 포함되지 않는다.

~~~
a ..< b
..<a
~~~
1에서부터 10까지 표현하는 방법은

~~~
1 ..< 11
~~~
이렇게 사용해 줘야한다.  

## .contains
- 범위안에 그 값이 있는지 없는지 확인해 주는 메서드이다.

~~~
let range = 0 ... 5
range.contains(7) // false
range.contains(1) // true
~~~


