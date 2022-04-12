---
title: Type Inference

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

Int 타입
~~~
let num = 123
type(of: num)
~~~

출력
~~~
Int.Type
~~~

String 타입
~~~
let str = "Swift"
type(of: str)
~~~

출력
~~~
String.Type
~~~

Bool 타입
~~~
let a = true
let b = false
type(of: a)
type(fo: b)
~~~

출력
~~~
Bool.Type
Bool.Type
~~~

Swift는 자료형을 추정해준다.

없으면 에러를 발생시키기 때문에 초기값을 설정해줘야한다.  
Ex)

~~~
let num: Int = 123
let value: Double
vaule = 12.3
~~~
하지만, 이렇게 추정해주는것도 시간이 든다. 간단한 프로젝트라면 상관이 없는데, 큰 프로젝트들은 이런 것들이 모여
메모리가 소요된다. 최적의 좋은 프로젝트를 만드려면 항상 타입을 명시해주자. 

