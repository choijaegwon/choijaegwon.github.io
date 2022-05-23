---
title: String Interpolation

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# String Interpolation  

파일의 크기를 저장한다고 가정.
~~~
var str = "12.34KB"

let size = 12.34
str = size + "KB" //에러가 발생(자료형이 다르기 떄문에)
str = String(size) + "KB" //이렇게 사용해야한다.
~~~
하지만 보통은,

~~~
str = "\(size)KB"
~~~
이렇게 사용한다. 문자열을 직관적으로 볼수 있기 때문이다.  
자동으로 값이 바뀐다. 하지만 단점은 원하는 포맷을 직접 정하지는 못한다.  

## Format Specifier
소수점 한자리까지 사용해라. f는 실수를 사용해라.
~~~
var str = "12.34KB"

str = String(format: "%.1fKB", size) 
~~~
출력하면
~~~
"12.3KB"
~~~

문자는 %@  
정수는 %d  
실수는 %f 
으로 나타낸다.  

~~~
let firstName = "Yoon-ah"
let lastName = "Lim"

let korFormat = "그녀의 이름은 %@ %@ 입니다."
let engFormat = "Her name is %@ %@."

String(format: korFormat, firstName, lastName)
String(format: engFormat, firstName, lastName)
~~~
출력하면
~~~
그녀의 이름은 Yoon-ah Lim 입니다.
Her name is Yoon-ah Lim.
~~~
이렇게 출력된다.  
한국은 이름순서가 뒤바뀌었는데, 이걸 정리를 해보면
~~~
let firstName = "Yoon-ah"
let lastName = "Lim"

let korFormat = "그녀의 이름은 %2$@ %1$@ 입니다."
let engFormat = "Her name is %1$@ %2$@."

String(format: korFormat, firstName, lastName)
String(format: engFormat, firstName, lastName)
~~~
이렇게 $를 사용해주면 쉽게 바꿀 수 있다.