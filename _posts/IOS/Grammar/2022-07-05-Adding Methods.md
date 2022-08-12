---
title: Adding Methods
categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Adding Methods
- 메서드는 클래스와 구조체 둘다 자유롭게 확장이 가능하다.

~~~
extension Double {
  func toFahrenheit() -> Double {
    return self * 9 / 5 + 32
  }
  
  func toCelsius() -> Double {
    return (self - 32) * 5 /9
  }

  static func converToFahrenheit(from celsius: Double) ->
    Double {
      return celsius.toFahrenheit()
    }
}

let c = 30.0
c.toFahrenheit() // 86
Double.converToFahrenheit(from: 30.0) //86
~~~
이렇게 Double 구조체를 확장해서 섭씨 온도로 바꿀 수 있다.

~~~
extension Date {
  func toString(format: String = "yyyyMMdd") -> String {
    let privateFormatter = DateFormatter()
    privateFormatter.dateFormat = format
    return privateFormatter.string(from: self)
  }
}

let today = Date() 
today.toString() //20220705
todat.toString(format: "MM/dd/yyy") //07/05/2022
~~~
