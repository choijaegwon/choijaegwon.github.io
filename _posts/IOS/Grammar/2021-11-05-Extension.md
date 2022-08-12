---
title: "Extension"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
  - Extension
---

## Extension
- 기능확장
- Struct, Class, Enum, Protocol  

숫자(int) 짝수, 홀수  

~~~
extension Int {
  var oddOrEven: String {
    if self % 2 == 0 {
      return "짝수"
    }
    return "홀수"
  }
}
~~~
이렇게해서 기능을 확장시키는 것이다.  
사용하는 방법은  

~~~
3.oddOrEven
~~~
이렇게 사용을 하는 것이다.
출력
~~~
"홀수"
~~~  

다른 예시로,  
UIColor가 있는데, 이건 화면에 버튼의 색이나, 텍스트의 색갈을 정하는 것이다.
~~~
extension UIColor {
  var mainColor1: UIColor {
    UIColor(red: 50/255, green: 70, 255, blud: 120/255, alpha: 1)
  }
}

var button = UIButton()

button.titleLabel?.textColor = UIColor().mainColor1 //Class는 인스턴스화 시켜줘야함.
~~~
이렇게 사용하면 같은 코드를 여러개 사용하는 것보다. 하나로 통합해서 쉽게 관리할 수 있다.  
위 코드를 Class화 시키면,  

~~~
extension UIColor {
  class var mainColor1: UIColor {
    UIColor(red: 50/255, green: 70, 255, blud: 120/255, alpha: 1)
  }
}

var button = UIButton()

button.titleLabel?.textColor = UIColor.mainColor1 //인스턴스화를 안시켜줘도 된다.
~~~
인스턴스 화를 안시켜줘도 된다.  
따라서 축약이 가능하다. 축약을하면
~~~
button.titleLabel?.textColor = UIColor.mainColor1
~~~
이부분이
~~~
button.titleLabel?.textColor = .mainColor1
~~~
이렇게 바뀔수 있다.__(static도 class와 같다.)__