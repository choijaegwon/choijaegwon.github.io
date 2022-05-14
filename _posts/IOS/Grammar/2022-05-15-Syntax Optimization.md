---
title: Syntax Optimization

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Syntax Optimization  
- 스위프트는 단순한 코드를 선호한다.  
- 따라서 압출된 코드가 되게 많다.  

## 예제1
~~~
var proModels = products.filter({ (name: String) -> Bool in
  return name.contains("Pro")
})
~~~
와
~~~
products.filter {
    $0.contains("Pro")
}
~~~
위 코드는 같다.  
->  파라미터형식과 리턴형을 생략할 수 있다.   
->  파라미터이름과 In 키워드는 생략할 수 있다.  
->  단일 리턴문만 있으면 리턴 키워드를 생략할 수 있다.  
->  마지막 파라미터라면 트레일링 클로저로 작성가능하다.  

## 예제2
~~~
proModels.sort(by: { (lhs: String, rhs: String) -> Bool in
  return lhs.caseInsensitiveCompare(rhs) == .orderedAscending
})
~~~
와
~~~
proModels.sort() {
  $0.caseInsensitiveCompare($1) == .orderedAscending
}
~~~
는 같은 코드이다.