---
title: String Editing 

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# String Editing
- 문자열 편집

~~~
var str = "Hello"
str.append(", ")
str // "Hello,"출력

let s = str.appendinging("Swift")
str // "Hello, "
s // "Hello,Swift"
~~~
append  -> 대상문자열을 직접 변경  
appending -> 대상문자열을 복사하여 변경
~~~
"File size is ".appendingFormat("%.1f", 12.3456) // "File size is 12.3"
~~~
문자열 리터럴에서 바로 호출해도된다 ing이여서 복사하여 사용하기 때문에

~~~
var str = "Hello Swift" 
str.insert(",", at: str.index(str.startIndex, offsetBy: 5)) // "Hello, Swift"
~~~
,가 추가된걸 볼 수 있다.

# Replacing Substrings
- 대부분 대소문자를 구분한다.
~~~
var str = "Hello, Objective-C"

if let range = str.range(of: "Objective-C") {
  str.replaceSubrange(range, with: "Swift")
}

str // "Hello,Swift"
~~~
범위를 아니까 통채로 바꿀 수 있다.

# Removing Substrings

~~~
var str = "Hello, Awesome Swift!!!"

let lastCharIndex = str.index(before: str.endIndex)

var removed =  str.remove(at: lastCharIndex)

removed // "!"
str // "Hello,Awesome Swift!!"
~~~
remove 는 Character를 return해서 조심해야한다.

