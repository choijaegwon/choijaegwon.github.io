---
title: Escaping Closure

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Escaping Closure  
- 시작과 종료가 일정하지 않다. 

~~~
func performNonEscaping(closure: () -> ()) {
  print("start")
  closure()
  print("end")
}

performNonEscaping {
  print("closure")
}
~~~
출력
~~~
start
closure
end
~~~
이렇게 함수바디에서 실행하고있는 클로져는 함수가 끝나기 전에 안에서 실행을 한다.  

~~~
func performEscaping(closure: @escaping () -> ()) {
  print("strart")

  DispatchQueue.main.asyncAfter(deadline: .now() + 3) {
    closure()
  }

  print("end")
}

performEscaping {
  print("closure")
}
~~~
함수의 흐름과 상관이 없어진다.
출력
~~~
start
end
closure
~~~
함수가 종료후 3초가 지난후 실행된다.  
이런 방식은 클로져가 함수의 실행을 벗어날 수 있다.  
따라서 활용이 무궁무진하다.