---
title: Optional Pattern

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Optional Pattern

~~~
if a == nil {

}
// 위아래 코드가 같다
if a == .none {

}

if a == 0 {

}
// 위아래 코드도 같다.
if a == .some(0) {

}
~~~
이를 활용해서 보면,
~~~
let a: Int? = 0
let b: Optional<Int> = 0

if case let x? = a{
  print(x) // "0\n"
}
~~~
a상수에 값이 저장되어 있으면 x를 바인딩하여 출력하게 되고, 
값이 저장되어 있지 않으면, 실행하지 않는다.

~~~
let list: [Int?] = [0, nil, nil, 3, nil, 5]

for item in in list {
  guard let x = item else { continue }
  print(x)
}
~~~
출력
~~~
0
3
5
~~~
guard문을 통해 옵셔널 바인딩을 한다.   
~~~
let list: [Int?] = [0, nil, nil, 3, nil, 5]

for case let x? in list {
  print(x)
}
~~~
이렇게 위코드를 간단하게 줄일 수 있다.
자세히 보면, list가 바인딩되면 정상적으로 출력을 하고 바인딩 되지 않으면, 출력을 하지 않는다. 
따라서 실행 결과는
~~~
0
3
5
~~~
로 위 코드랑 동일 하다.
