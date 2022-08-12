---
title: "compactMap"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## compactMap  

## 일반 map  
- 변형시키는 값으로 nil 도 넣는다


~~~
var myArray = ["one", "2", "three", "4"]

let intArray = myArray.map({ (item: String) in 
                    return Int(item)})
print(intArray)
~~~  

출력  

~~~
[nil, Optional(2), nil, Optional(4)]
~~~  

## compactMap
- 변형시키는 값이 nil이면 해당 요소를 뺀다.

~~~
var myArray = ["one", "2", "three", "4"]

let onlyIntArray = myArray.compactMap({(item: String) in
                        return Int(item)})
print(onlyIntArray)
~~~  

출력  

~~~
[2, 4]
~~~  

