---
title: Dictionary

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Dictionary
- 키와 값이 있다.
- 키는 유일값이지만, 값은 중복이 가능하다.
- 값의 자료형이 같아야한다.

~~~
var dict = ["A": "Apple", "B": "Banana"]
dict = [:]

// 빈 딕셔너리 만들기
let dict1: Dictionary<String, Int>
let dict2: [String: Int]
let dict3 = [String: String]()
~~~

## Inspecting a Dictionary

~~~
// 딕셔너리의 개수를 알고싶으면
dict.count
// 딕셔너리가 비어있는지 확인하고싶으면
dict.isEmpty
~~~

## Accessing Keys and Values

~~~
dict["A"] // Apple
dict["Apple"] // nil

let a = dict["E"] // nil 
a -> 옵셔널 String 값이 나온다.
let b = dict["E", default: "Empty"] // 정상값이 저장된다.
~~~

## Adding Keys and Values

~~~
var words = [String: String]()

words["A"] = "Apple"
words["B"] = "Banana"

words.count // 2
words // ["A": "Apple", "B" : "Banana"]

words["B"] = "Ball" // 이렇게 사용하면
words // ["A": "Apple", "B" : "Ball"] 이렇게 변경된다.
~~~

## Removing Keys and Values

~~~
words // ["A": "Apple", "B" : "Ball"]
words["B"] = nil 

wrods // ["A": "Apple"]
wrods.removeAll() // 모든값 삭제하기
~~~

## Comparing Dictionaries

~~~
let a = ["A": "Apple", "B", "Banana", "C": "City"]
let b = ["A": "Apple", "C", "City", "B": "banana]

a == b // false
a != b // true -> 대소문자 비교해서 그럼
~~~