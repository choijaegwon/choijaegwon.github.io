---
title: Tuple Decomposition

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Tuple Decomposition
- 튜플에 저장된 값을 개별상수나, 개별변수에 따로 저장하는 것이다.

~~~
let data = ("<html>" , 200, "OK", 12.34)
~~~
위 코드를 
~~~
let body = data.0
let code = data.1
let message = data.2
let size = data.3
~~~
이렇게 저장할 순 있다 하지만, 되게 복잡해 보이고 손이 많이 간다.  
따라서, 이렇게

~~~
let (body, code, message, size) = data
~~~
이렇게 사용하면 위 코드랑 똑같이 저장이 된다.
