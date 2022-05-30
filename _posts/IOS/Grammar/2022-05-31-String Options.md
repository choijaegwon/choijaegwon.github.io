---
title: String Options

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# String Options  

~~~
"A" == "a" // false -> 대소문자를 구분하기 때문
"A".caseInsensitiveCompare("a") == .orderedSame // true
"A".compare("a", options: [.caseInsensitive]) == .orderedSame//true
~~~

# Literal Option

~~~
let a = "\u{D55C}" //한
let b = "\u{1112}\u{1161}\u{11AB}" //한

a == b // true
a.compare(b) == .orderedSame // true
~~~
스위프트에서는 결과값도 비교해주지만, Object-C는 결과값이 다르면 false를 나타낸다.  
따라서 스위프트에서 Objcet-C 처럼 해주려면, Literal를 사용하면 된다.  
~~~
a.compare(b, options: [.literal]) == .orderedSame // false
~~~

# Backwards Options
- backwards 문자열의 검색 방향을 바꾸는 메서드
~~~
let korean = "행복하세요"
let english = "Be happy"

if let range = english.range(of: "p") {
  english.distance(from: english.startIndex, to: range.lowerBound)
} //5

if let range = english.range(of: "p", options: [.backwards]) {
  english.distance(from: english.startIndex, to: range.lowerBound)
} //6
~~~

# Anchored Option
- 검색범위를 문자열 시작이나 끝으로 지정이가능하다

~~~
let str = "Swift Programming"

if let result = str.range(of: "Swift") {
  print(str.distance(from: str.stratIndex, to: result.lowerBound))
} esle {
  print("not found")
} // "0\n"

if let result = str.range(of: "Swift", options: [.backwards]) {
  print(str.distance(from: str.stratIndex, to: result.lowerBound))
} esle {
  print("not found")
} // "0\n"

if let result = str.range(of: "Swift", options: [.anchored]) {
  print(str.distance(from: str.stratIndex, to: result.lowerBound))
} esle {
  print("not found")
} // "0\n"

if let result = str.range(of: "Swift", options: [.anchored, .backwards]) {
  print(str.distance(from: str.stratIndex, to: result.lowerBound))
} esle {
  print("not found")
} // "not found\n" -> 마지막 부분만 검색한것이다.
~~~

# Numeric Option
- 숫자 차체를 비교할수 있게 해 준다.
~~~
"A" < "B" // true
"a" < "B" // false -> 아스키문자는 a가 더 크다.

let file9 = "file9.txt"
let file10 = "file10.txt" 

file9 < file10 // false -> 숫자가 더 커도 9가 더 크기때문에 False

file9.compare(file10) == .orderedAscending // false
file9.compare(file10, options:[.numeric]) == .orderedAscending //true
~~~

# Diacritic Insensitive
- 발음기호를 무시하고 비교하고싶을때
~~~
let a = "Cafe"
let b = "Cafè"

a == b //false
a.compare(b) == .orderedSame // false
a.compare(b, options: [.diacriticInsensitive]) == .orderedSame // true
~~~

# Forced Ordering Option
- 강제정렬
- 전체옵션을 적용했을떄, 같은문자열로 판단된다면, 일부 옵션을 무시하고 최대한 문자열의 순서를 파악할수있는걸 리턴해준다.
~~~
let upper = "STRING"
let lower = "string"

upper == lower // fasle
upper.compare(lower, optiuons: [.caseInsensitive]) == .orderedSame // true
upper.compare(lower, optiuons: [.caseInsensitive, .forcedOrdering]) == .orderedSame // false
~~~

# Regular Expression
- 해당패턴이 존재한다면 범위를 리턴해준다.

~~~
let emailPattern = "([0-9a-zA-X_-]+)@([0-9a-zA-Z_-]+)(\\.[0-9a-zA-Z_-]+){1,2}"
let emailAddress = "user@example.com"

if let _ = emailAddress.range(of: emailPattern) {
  print("found")
} else {
  print("not found")
} // "not found\n"

// 첫번째 파라미터로 전달된 문자열을 정규식으로 처리한다.
// 정규식과일치하면 첫번쨰 범위가 리턴된다.
if let _ = emailAddress.range(of: emailPattern, options[.regularExpression]) {
  print("found")
} else {
  print("not found")
} // "found"
~~~