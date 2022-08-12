---
title: "Set의intersection"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## Set의intersection  

~~~
// 배열
let myFriends = ["철수", "영희", "수잔", "제시카"]
let yourFriends = ["철수", "수잔", "제니퍼", "존시나"]

// 배열을 set으로 만들기
let myFriendsSet = Set(myFriends)
let yourFriendsSet = Set(yourFriends)

// 인터섹션으로 중복은 제거하고 합치기
let commonFriends = myFriendsSet.intersection(yourFriendsSet)

print(commonFriends)
~~~  

출력  
~~~
["수잔", "철수"]
~~~  