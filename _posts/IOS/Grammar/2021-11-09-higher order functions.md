---
title: "higher order functions"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
  - higher order functions
---

# higher order functions(고차함수)
## names를 가지고 끝에 님을 붙이고싶을때,  

~~~
let names = ["kim", "lee", "min", "john"]

// map ->
let names2 = names.map { name in
  name + "님"
}
~~~
출력하면
~~~
["kim님", "lee님", "min님", "john님"] 
~~~
이렇게 된다.  

## 글자의 개수로 표현해보면,  

~~~
let names = ["kim", "lee", "min", "john"]

// map ->
let names3 = names.map { name in
  name.count
}
~~~
출력하면
~~~
[3, 3, 3, 4]
~~~
이렇게 출력된다.  

## Bool타입으로도 할수가 있다.  
~~~
let names = ["kim", "lee", "min", "john"]

// map ->
let names4 = names.map{ name in
  name.count > 3
}
~~~
출력하면
~~~
[false, false, false, true]
~~~
이렇게 출력된다.  


## filter -> 거른다.
~~~
let names = ["kim", "lee", "min", "john"]

let filterNames = names.filter { (name) -> Bool in
  name.count > 3
}

filterNames
~~~
출력하면
~~~
["john"]
~~~
이 출력된다. 3보다큰게 "john"하나여가지고 "john"이 나온다.  

## reduce -> 하나로 뭉친다. or 통합한다.
~~~
let names = ["kim", "lee", "min", "john"]

let sumName = names.reduce("") { (first, second) in
  return first + second
}
~~~
시작하는값과, 받는값을 정해야한다.
출력하면
~~~
"kimleeminjohn"
~~~
이렇게 출력이 된다. ""에 시작하고싶은 글자를 넣으면,  
~~~
let names = ["kim", "lee", "min", "john"]

let sumName = names.reduce("hi") { (first, second) in
  return first + second
}
~~~
출력하면
~~~
"hikimleeminjohn"
~~~
이렇게 앞에 붙어서 출력이 가능하다.  
하지만 앞에서 배웠던것 처럼,  
~~~
let sumName = names.reduce("hi") { (first, second) in
  return first + second
}
~~~
이부분은 생략이 가능한다. 생략해보면,  
~~~
let sumName = names.reduce("hi") { 
  $0 + $1
}
~~~
이렇게 생략 가능하다.  

숫자에 적용을 해 보면,  
~~~
let numberArr = [1, 2, 3, 4, 5]
let sumNum = numberArr.reduce(0) { $0 + $1 }
sumNum
~~~
출력하면
~~~
15
~~~
이렇게 나온다. 즉 숫자에 적용해서 사용할 수도 있다.  

## compactMap(nil을 없앤다.)
~~~
let numberArr = [1, 2, 3, 4, 5, nil, 6, nil, 8]
let sumNum = numberArr.reduce(0) { $0 + ($1 ?? 0) }
sumNum
~~~
출력하면
~~~
[1, 2, 3, 4, 5, 6, 8]
~~~
원래 nil이 포함되어 있으면 오류가 뜨지만 이렇게, ($1 ?? 0) 지정해주면 오류가 뜨지않는다.  
compactMap은 위에있는 nil자체를 없애고 싶을때 사용한다.

~~~
let numberArr = [1, 2, 3, 4, 5, nil, 6, nil, 8]
let numbers = numberArr.compactMap { (num) in 
  retrun num}
}
numbers
~~~
출력해보면
~~~
[1, 2, 3, 4, 5, 6, 8]
~~~
위에와 똑같다. 다시 줄여보면,  
~~~
let numberArr = [1, 2, 3, 4, 5, nil, 6, nil, 8]
let numbers = numberArr.compactMap { $0 }
numbers
~~~
이렇게만 적어도 
~~~
[1, 2, 3, 4, 5, 6, 8]
~~~
이렇게 같은 결과값이 나온다.  

## flatmap(단순화)
~~~
let numbers2 = [[1,2,3], [4, 5, 6]]

let flatNum = numbers2.flatmap{ $0 }
flatNum
~~~
출력해보면
~~~
[1, 2, 3, 4, 5, 6]
~~~
이렇게 2중 구조로 되어있는걸 풀어 줄 수 있다.