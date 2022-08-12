---
title: if Statement

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# if로만 구현하기

간단한 로그인 구현  
아이디와 비밀번호는 고정값이라고 생각한다.
~~~
let id = "root" 
let password = "1234qwer"

if id == "root" {
  print("valid id") // "valid id\n"
}

if password == "1234qwer" {
  print("valid password") // "valid password\n"
}

if id == "root" && password == "1234qwer" { //아이디와 비밀번호가 같으면
  print("go to admin page")
} 

if id != "root" || password != "1234qwer" { //아이디와 비밀번호가 다르면
  print("incorrect value")
}
~~~  

# if else로 구현하기

~~~
let id = "root" 
let password = "1234qwer"

if id == "root" && password == "1234qwer" { //아이디와 비밀번호가 같으면
  print("go to admin page")
} else {
  print("incorrect value")
}
~~~
이렇게 짧게 만들수 있다.

# if else if else 구현하기
~~~
let num = 123

if num >= 0 {
  print("positive number or zero")
} else if num % 2 == 0 && num >= 0 {
  print("positive even number")
} else if num % 2 == 1 && num >= 0 {
  print("positvie odd number)
} else {
  print("negative number")
}
~~~
를 압축시키면,

~~~
let num = 123

if num >= 0 {
  print("positive number or zero")

  if num % 2 == 0 {
    print("positive even number")
  } else {
  print("positvie odd number)
  }

} else {
  print("negative number")
}
~~~
이렇게 만들 수 있다.

## if 문은 까다로운 조건을 맨위로 올려서 먼저 처리해야한다.  
