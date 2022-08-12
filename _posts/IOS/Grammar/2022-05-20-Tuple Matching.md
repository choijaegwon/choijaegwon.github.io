---
title: Tuple Matching

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Tuple Matching  

해상도를 비교해서 4K인지 출력하는 코드
~~~
let resolution = (3840.0, 2160.0)

let resolution.0 == 3840 && resoltuon.1 == 2160 {
  print("4K") //4K가 출력된다.
}
~~~
위 코드를 
~~~
let resolution = (3840.0, 2160.0)

switch resolution {
  case (3840, 2160):
    print("4K")
  default:
    break
}
~~~
이렇게 바꿔도 된다. 훨씬 더 깔끔하고 가독성이 좋아진다.  
새로운 case도 추가 할수 있다.