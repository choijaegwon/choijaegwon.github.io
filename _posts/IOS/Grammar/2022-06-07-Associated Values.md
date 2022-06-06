---
title: Associated Values

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Enumeration Types

## Associated Values

~~~
enum VideoInterface: String {
  case dvi = "1028x768"
  case hdmi = "2048x1536"
  case displayPort = "3840x2160"
}
~~~
이런방식으로 저장을 해버리면 String밖에 안되기 떄문에 좋은 방법은 아니다.  
따라서 바꿔보면

~~~
enum VideoInterface: String {
  case dvi(width: Int, height: Int)
  case hdmi(Int, Int, Double, Bool)
  case displayPort(CGSize)
}

var input = VideoInterface.dvi(width 2048, height: 1536)

switch input {
  case .div(2048, 1536):
    print("dvi 2048 x 1536")
  case .dvi(2048, _):
    print("dvi 2048 x Any")
  case .dvi:
    print("dvi")
}
~~~
이런 방식으로 사용이 된다고 생각하면 된다.