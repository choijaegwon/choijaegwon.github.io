---
title: for-in Loop

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# For-In Loops

"hello"를 한번 출력하고싶으면
~~~
print("hello")
~~~

"hello"를 두번 출력하고싶으면
~~~
print("hello")
print("hello")
~~~

하지만 "hello"를 100번 출력하고싶으면..?
~~~
for index in 1 ... 100 {
  print("hello")
}
~~~
이렇게 이럴때 반복문을 사용하면 된다.

## 2의 10승 예제
~~~
let power = 10
var result = 1

for _ in 1 ... power {
  result *= 2
}

result //1024
~~~

## 0에서 10까지 지정한후, 짝수만 출력하기

~~~
for num in stride(from: 0, to: 10, by: 2) {
  print(num)
}
~~~
출력
~~~
2
4
6
8
10
~~~

## 컬렉션도 범위로 만들수 있다 

~~~
let list = ["Apple", "Banana", "Orange"]
for fruit in list {
  print(fruit)
}
~~~
출력
~~~
Apple
Banana
Orange
~~~

## 구구단

~~~
for i in 2 ... 9 {
  for i in 1 ... 9 {
    print("\(i) * \(j) = \(i * j))
  }
}
~~~
출력
~~~
2 * 1 = 2
2 * 2 = 4
...
...
...
9 * 8 = 72
9 * 9 = 81
~~~


