---
title: Variadic Parameters

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Variadic Parameters
- 가변파라미터
- 선언하는 방법은 파라미터뒤에...을 붙이면 된다.
- 하나의 파라미터로 두개이상의 Argument를 전달할 수있다.
- Argument는 배열형태로 전달된다.
- 가변파라미터는 개별함수마다 1개만 설정할 수 있다.
- 가변파라미터는 기본값을 가질 수 없다.

~~~
print("Hello") // Argument는 1개 파라미터도 1개이다.

print("Hello", "Swift") // Argument는 2개 파라미터는 1개이다.
~~~

~~~
func printSum(of nums: Int...) {
  var sum = 0 
  for num in nums {
    sum += num
  }
  print(sum)
}

print(of: 1, 2, 3)
~~~
출력
~~~
6
~~~