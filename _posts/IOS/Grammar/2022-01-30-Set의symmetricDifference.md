---
title: "Set의symmetricDifference"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## Set의symmetricDifference  

~~~
// 배열
let myFriends = ["철수", "영희", "수잔", "제시카"]
let yourFriends = ["철수", "수잔", "제니퍼", "존시나"]

// 배열을 set으로 만들기
let myFriendsSet = Set(myFriends)
let yourFriendsSet = Set(yourFriends)

// 중복되는 녀석들은 제거하고 합치기
let exceptDuplicateFriends = myFriendsSet.symmetricDifference(yourFriendsSet)

print(exceptDuplicateFriends)
~~~  

출력  
~~~
["제니퍼", "영희", "존시나", "제시카"]
~~~  