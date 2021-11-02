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

---  
옵셔널은 그냥 사용할 수 없는 경우가 많이 있다.  
ex)  
~~~
var a = 10  
var b = 20  
  
var c = a + b
~~~  
이건 잘 작동하지만,  
~~~
var a: Int? = 10  
var b: Int? = 20  
  
var c = a + b
~~~  
이렇게 사용하려고하면 작동하지 않는다 그이유는  
// Int? -> Int  
// String? -> String
이런식으로 unwrapping을 해야하기 때문이다.  
이럴때 쓰는 문법이 따로 있는데 그게 바로, __coalesce__ 이다.  
## coalesce 
예를들어, 
~~~
var c = (a ?? 0)
~~~  
이런방식으로 사용하는 것이다 이게 하나의 문법인데,  
a라는 값이 있으면 그값을 사용하는데 없으면 0으로 대체해서 사용하는 것이다.  
따라서,  
~~~
var a: Int? = 10  
var b: Int? = 20  
  
var c = (a ?? 0) + (b ?? 0)
~~~  
이렇게 해야 잘 작동이 된다.  
## force unwrap(강제로 변경한다)
~~~
var d = a! + b!
~~~  
이렇게 사용해야한다. !란 a라는 값이 무조건 있는 상태로 가정하고 사용하는 것이다.  
만약에 없이 사용한다고 치면, 그냥 앱 자체가 죽어버리고 변수가 망가진다.  
즉, 무조건 값이 있다고 생각하고 사용해야한다.  

---  
~~~
var a: Int? = 20
if a != nul {
  print(a)
}
~~~  
의 출력값은 Optional(20)이고,  
~~~
if let hasNumber = a {
  print(hasNumber)
}
~~~  
의 출력값은 20이다. 그 이유는 let이라는 unwrapping을 하는 문법이 들어있어서이다.
var로 할수도있다.
~~~
if var hasNumber = a {
  hasNumber = hasNumber * 2
  print(hasNumber)
}
~~~  
let은 상수라서 값을 변경못하는데 var는 변수라서 값을 변경할수 있다.  
따라서 변경해서 사용하고싶으면 var를 써야한다.  

---
## guard let
guard 안에 값이 있으면 그 값을 출력하지만, 그값이 없으면 아예 출력 자체를 하지 않는다.
~~~
var a: Int? = 20

func testFunc(){
  guard let hasNumber = a else {
    return
  }
  print(hasNumber)
  print("end")
}
~~~
20이 있으므로 출력값은
~~~
20
end
~~~
가 나오고 만약 위에 20을 지우면 출력값자체가 나오지 않는다. 그 이유는 값이 없기 때문에