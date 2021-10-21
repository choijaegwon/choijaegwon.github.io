---
title: "기본 문법(Optionals)"

categories:
  - UIkit
tags:
  - IOS
  - Swift
  - Optionals
---

## Optionals
- 값이 있을수도 있고, 없을수도 있다.
- 값이 있다.  
0 -> 다쓴 상태인 값.  
- 값이 없다.  
nil -> 아예 값이 없는 것.  
~~~
ex) 값이 없는 상태 체크에 0을 넣으면 -> 틀린 로직이다.
var myAge: Int = 0
if myAge == 0 {
  //alert - 나이를 입력해 주세요.
}
~~~  
따라서
~~~
var myAge: Int? = 0
if myAge == nil {
  // alert - 나이를 입력해 주세요.
}
~~~  
이런 방식으로 사용해야 한다.  
비슷한 느낌으로
~~~
var myName: String? = " " //빈스트링
if myName == ""{
  //이름을 입력해주세요.
}
~~~
위에 예제는 틀린 예제이고, 
~~~
var myName: String? = " "
if myName == nul {
  //이름을 입력해주세요.
}
~~~  
이런 방식이 맞는거다.
