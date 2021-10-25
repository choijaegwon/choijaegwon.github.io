---
title: "기본 문법(Dictionary)"

categories:
  - UIkit
tags:
  - IOS
  - Swift
  - Dictionary
---

## Dictionary
- Keys, Values로 구성되어있다.  
- 순서가 필요 없다.  

~~~
var namesOfStreet = [String : Any]()

namesOfStreet["302ro"] = "1st Street"
namesOfStreet["303ro"] = "2nd Street"
namesOfStreet["304ro"] = 3
~~~
출력값
~~~
["303ro":"2nd Street", "302ro":"1st Street","304ro":3]
~~~
이렇게 출력이 된다. 오타가 나거나 없는 Key를 호출하면 nil로 처리 된다.  
~~~
var namesOfStreet2 = ["a" : 1, "b" : 2, "c" : 3]
~~~
이렇게 처리할 수도 있다.  
따로 Values에 nil을 줘 버리면, 값 자체가 없어져서 출력이 불가능 하다.  

따로 Key값만 보고싶으면
~~~
var namesOfStreet = [String : Any]()

namesOfStreet["302ro"] = "1st Street"
namesOfStreet["303ro"] = "2nd Street"
nameOfStreet.keys
~~~
출력을 해보면
~~~
Dictionary.Keys(["303ro","302ro"])
~~~
라고 출력이 된다.  
만약에 하나하나 키와 값을 보고싶을땐 간단히 __for__ 문을 사용하면 된다.  
~~~
var namesOfStreet = [String : Any]()

namesOfStreet["302ro"] = "1st Street"
namesOfStreet["303ro"] = "2nd Street"

for dic in namesOfStreet {
  print(dic)
}
~~~
출력값을 보면
~~~
(key: "303ro", values: "2nd Street")
(key: "302ro", values: "1st Street")
~~~
이런 식으로 출력해서 확인할 수 있다.