---
title: Multiline String Literals

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Multiline String Literals
- 명시적으로 띄어쓰기를 할 수 있다.

보통은 
~~~
let loremIpsum = "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua."
~~~
이렇게 길게 쓰면 한줄로 이어진다. 따라서 글을 읽기가 힘들다 따라서 \n으로 명시적 줄바꿈을 해주는데,  
그렇게 사용을하면 중간에 들어가서 보기가 어렵다  따라서 Multiline(""")를 활용할 수 있다.

~~~
let multiline = """
Lorem ipsum dolor sit amet, 
consectetur adipiscing elit, sed do eiusmod 
tempor incididunt ut labore et dolore magna aliqua.
"""
~~~
이런식으로 사용을 하면 된다. 그러면 원하는 중간에 명시적으로 표현할 수 있다.  
마지막 """은 첫번쨰 줄과 동일선상에 있거나, 그 앞에 있어야한다. 아니면 에러가 발생된다.