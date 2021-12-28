---
title: "sort, sorted"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## sort, sorted  
- sort는 호출된 배열을 변경하여 값들을 정렬한다.  
- sorted는 정렬된 값으로 된 배열의 사본을 리턴한다.


~~~
var myArray = [1,4,3,2,5,9,7,6,8,10]
// sorted를 통해 오름차순으로 정렬된 새 콜렉션을 반환한다.
var filteredArray = myArray.sorted()
print("myArray : \(myArray)")
print("filteredArray : \(filteredArray)")
~~~  

출력하면  
~~~
myArray : [1,4,3,2,5,9,7,6,8,10]
filteredArray : [1,2,3,4,5,6,7,8,9,10]
~~~   

콜렌션 내의 데이터 들을 번갈아 가면서 돌아 반호나 값이 true 가 나올때 해당 하는 녀석을 넣게 된다.  
그래서 내림차순으로 정렬이 된다.  

~~~
var myArray = [1,4,3,2,5,9,7,6,8,10]
var filteredArray = myArray.sorted()
var descendingArray = myArray.sorted(by: { (someValue:Int, otherValue:Int) -> Bool in
    return somValue > otherValue
})
print("descendingArray : \(descendingArray)")
~~~  

출력하면
~~~
descendingArray : [10,9,8,7,6,5,4,3,2,1]
~~~  

클로져 부분 축약 버전  

~~~
var myArray = [1,4,3,2,5,9,7,6,8,10]
var filteredArray = myArray.sorted()
var descendingArray = myArray.sorted(by: { (someValue:Int, otherValue:Int) -> Bool in
    return somValue > otherValue
})
var myDescendingArray = myArray.sorted(by:{
  return $0 > $1
})
print("myDescendingArray : \(myDescendingArray)")
~~~  

출력하면  
~~~
myDescendingArray : [10,9,8,7,6,5,4,3,2,1]
~~~  

&#62; 를 통해 보다 간편하게 정렬이 가능하다  
~~~
var myArray = [1,4,3,2,5,9,7,6,8,10]
var filteredArray = myArray.sorted()
var descendingArray = myArray.sorted(by: { (someValue:Int, otherValue:Int) -> Bool in
    return somValue > otherValue
})
var myDescendingArray = myArray.sorted(by:{
  return $0 > $1
})
var shortenDescendingArray = myArray.sorted(by: >)
print("shortenDescendingArray : \(shortenDescendingArray)")
~~~  

출력하면  
~~~
shortenDescendingArray : [10,9,8,7,6,5,4,3,2,1]
~~~  

sort() 메소드를 통해 해당 배열 자체를 정렬한다.
~~~
myArray.sort()
myArray.sort(by: >)
myArray.sort(by: {
  return $0 < $1
})
myArray.sorted(by: { (someValue:Int, otherValue:Int) -> Bool in
    return somValue > otherValue
})
~~~