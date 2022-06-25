---
title: Overloading
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Overloading
- 동일한 이름의 함수를 지원한다
- 파라미터의 형식티 다르면 같은 이름을 사용해도 된다.
- 1.함수 이름이 동일하면 파라미터 수로 식별
- 2.함수이름, 파라미터 수가 동일하면 파라미터 자료형으로 식별
- 3.함수 이름, 파라미터가 동일하면 Argument Label로 식별
- 4.함수 이름, 파라미터, Argument Label이 동일하면 리턴형으로 식별

~~~
func process(value: Int) {

}

func process(value: String) {
  
}
~~~
위에 두개의 동일한함수 이름을 사용할 수 있다.  
스위프트에서는 Overloading을 지원하기 떄문이다.
위에 4가지 법칙을 사용하면 된다.    
하지만 4번째는 지양하는게 좋다. 