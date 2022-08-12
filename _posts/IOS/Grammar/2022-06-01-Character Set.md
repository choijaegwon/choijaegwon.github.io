---
title: Character Set

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Character Set
- 문자열 검색이나 잘못된 문자를 삭제할떄 활용

~~~
let a = CharacterSet.uppercaseLetters
let b = a.inverted 

//검색코드구현

var str =  "loRem Ipsum"
var charSet = CharacterSet.uppercaseLetters

if let range = str.rangeOfCharacter(from: charSet) {
  print(str.distance(from: str.startIndex, to: range.lowerBound))
} // "2\n"

if let range = str.rangeOfCharacter(from: charSet, options: [.backwards]) {
  print(str.distance(from: str.startIndex, to: range.lowerBound))
} // "6\n"

str = " A p p l e "
charSet = .whitespaces

let trimmed = str.trimmingCharacters(in: charSet) // "Apple"
print(trimmed) // "Apple\n"

var editTarget = CharacterSet.uppercaseLetters
editTarget.insert("#")
editTarget.insert(charactersIn: "~!@")

editTarget.remove("A")
editTarget.remove(charactersIn: "BCD")

let customCharSet = CharacterSet(charactersIn: "@.") 
let email = "userId@example.com"

let components = email.components(separatedBy: customCharSet) // ["userid", "exmaple", "com"]
~~~