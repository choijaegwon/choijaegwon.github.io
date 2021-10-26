---
title: "기본 문법(Control Flow)"

categories:
  - UIkit
tags:
  - IOS
  - Swift
  - Control Flow
---

# Control Flow
## for
~~~
let name "banana"
for char in name {
    print(char)
}
~~~
출력해보면
~~~
b
a
n
a
n
a
~~~
가 된다.  
이를 이용하여 다양하게 활용할 수 있는데,
~~~
let number = "123456"

for haha in number {
  print( (Int(String(haha)) ?? 0)* 10 )
}
~~~
을 출력해보면
~~~
10
20
30
40
50
60
~~~
이 된다.  
이건 haha가 String으로 되어있긴한데  
String.Element값으로 되어있어서 뽑아 올수 없다.  
따라서, 순수 String값으로 바꿔준 다음,  
Int형으로 한번 감싸주면 된다.  
하지만 Optioncal타입 이기 때문에 이걸 (변수 ?? 0)문법을 사용해서 Optional을 제거해줘야한다.  
그러면 저렇게 출력이 가능하다.

---  

### Array이용
~~~
let names = ["Choi", "jae", "gwon"]

for name in names {
  print(name + "님")
}
~~~
출력하면
~~~
Choi님
jae님
gwon님
~~~
이렇게된다.  

---

### Dictionary이용
~~~
let numberOfLegs = ["ant" : 6, "dog" : 4]

for dic in numberOfLegs {
  print(dic)
}
~~~
출력하면
~~~
(key: "dog", values: 4)
(key: "ant", values: 6)
~~~
으로 출력이 된다.  

## while(주의) - 왠만하면 사용하지 않는게 좋음.
- 프리징(멈춰버림)이 걸릴수 있다.
- 무한으로 반복문안에서 계속 실행될수 있다.  

사용법  
~~~
while (조건) {
    print("계속 실행") // <<-참이면 계속 실행
}
~~~
예를 들어,
~~~
let a = 0
while (a == 0) {
    print("계속 실행")
}
~~~
출력하면
~~~
계속 실행
.
.
.
계속 실행
~~~
이렇게 되서 아예 안된다.  
즉, a==0 이면 ture면 안에 있는 값을 계속 실행한다.  

## Switch
- 조건에 케이스를 만들어서 나눈다.

~~~
switch value {
  case 패턴:
  코드
  default:
  코드
}
~~~
예를 들어,
~~~
let b = "b"

switch b {
  case "b":
    print("b")
  case "c":
    print("c")
  default:
    print("other")
}
~~~
를 출력해보면,
~~~
b
~~~
가 출력된다.  
예를 들어,
~~~
let b = "c"

switch b {
  case "b":
    print("b")
  case "c":
    print("c")
  default:
    print("other")
}
~~~
를 출력해보면,
~~~
c
~~~
가 출력 된다.  
만약에 "b"도 아니고, "c"도 아니면, other가 출력된다.  
~~~
let b = "a"

switch b {
  case "a", "b", "c":
    print("a or b or c")
  case "d":
    print("d")
  default:
    print("other")
}
~~~
를 출력해보면,
~~~
a or b or c
~~~
이처럼 한 case안에 여러가지 조건도 넣을 수 있다.  
또 숫자도 가능하다.
~~~
let b = 4

switch b {
  case 1:
    print("num 1")
  case 2...5:
    print("num 2~5")
  default:
    print("other")
}
~~~
를 출력해보면,
~~~
num 2~5
~~~