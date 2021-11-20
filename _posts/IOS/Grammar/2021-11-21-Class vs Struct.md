---
title: "Class vs Struct"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## sturct
~~~
sturct YoutuberStruct {
  var name : String
  var subscribersCount : Int
}

var devMin = YoutuberStruct(name: "류민희", subscribersCount: "99999")

var devMinClone = devMin

print("값 넣기 전 devMinClone.name : \(devMinClone.name)")

devMinClone.name = "하하"

print("값 넣은 후 devMinClone.name : \(devMinClone.name)")
print("값 넣은 후 devMin.name : \(devMin.name)")
~~~
출력  
~~~
값 넣기 전 devMinClone.name : 류민희
값 넣은 후 devMinClone.name : 하하
값 넣은 후 devMin.name : 류민희
~~~
__sturct는__ 값을 복사하기 때문에 __값이 다르다.__  

## Class  

~~~
Class YoutuberClass {
  var name : String
  var subscribersCount : Int

  init(name: String, subscribersCount: Int) {
    self.name = name
    self.subscribersCount = subscribersCount
  }
}

var Mins = YoutuberStruct(name: "류민희", subscribersCount: "99999")
var MinsClone = Mins

print("값 넣기 전 MinsClone.name : \(MinsClone.name)")
MinsClone.name = "하하"
print("값 넣은 후 MinsClone.name : \(MinsClone.name)")
print("값 넣은 후 Mins.name : \(Mins.name))
~~~  
출력
~~~
값 넣기 전 MinsClone.name : 류민희
값 넣은 후 MinsClone.name : 하하
값 넣은 후 Mins.name : 하하
~~~
생성자 - 즉 메모리에 올린다.  
init으로 매개변수를 가진 생성자 메소드를 만들어야  
매개변수를 넣어서 그 값을 가진 객체를 만들수 있다.  
__class는__  서로 연결되어 있어서, __값이 같다.__

