---
title: Value Types vs Reference Types
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Value Types vs Reference Types

~~~
struct PositionValue {
  var x = 0.0
  var y = 0.0
}

class PositionObject {
  var x = 0.0
  var y = 0.0
}

var v = PositionValue // 0으로 초기화
var o = PositionObject // 0으로 초기화

var v2 = v // 0으로초기화
var o2 = o // 0으로 초기화
~~~
똑같이 복사해서 넣어본 후, 코드를 작성해 보면,  

~~~
v2.x = 12
v2.y = 34

v // x=0,  y=0
v2 // x=12, y=34
~~~
값형식으로 v2를 바꿔도 v에는 아무런 영향을 미치지 않는다.  
하지만 class는  

~~~
o2.x = 12
o2.y = 34

o // x=12, y=34
o2 // x=12, y=34
~~~
참조형식이라 o2를 바꾸면 o도 같이 바뀌어 영향을 끼친다.  
원본을 저장하기 때문이다.  