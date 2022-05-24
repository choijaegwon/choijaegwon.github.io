---
title: String Indices

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# String Indices  

~~~
let str = "Swift" 

let firstCh = str[str.startIndex]
print(firstCH)
~~~
출력하면
~~~
S
~~~
가 출력된다. 하지만

~~~
let lastCh = str[str.endIndex]
print(lastch)
~~~
를하면 마지막 문자가 나타나지않고 에러가 발생한다.  
그 이유는 마지막 문자를 나타내는게 아니라 그 다음 문자를 나타내기 떄문이다. 따라서
~~~
let lastCharIndex = str.index(before: str.endIndex)
let lastCh = str[lastCharIndex]
print(lastCh)
~~~
이렇게 사용해야지 에러가 안뜨고 마지막 문자인 t가 출력된다.  
두번째 문자를 출력해보면,

~~~
let secondCharIndex = str.index(after: str.startIndex)
let secondCh = str[secondCharIndex]
print(secondCh)
~~~
이렇게 하면 두번쨰 문자인 w가 출력이 된다.  
세번쨰 문자는 두번쨰 문자를 활용해서 출력할 수 있다.  
~~~
var thirdCharIndex = str.index(str.startIndex, offsetBy: 2)
var thirdCh = str[thirdCharIndex]
print(thirdCh) 
~~~
출력
~~~
i
~~~
이렇게 offsetBy를 이용해서 출력할수도 있다.