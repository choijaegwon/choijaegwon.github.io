---
title: "KaKao_Test"

categories:
  - SimpleResult
tags:
  - SimpleResult
---  

![KaKao_Test](https://user-images.githubusercontent.com/68246962/155585238-fb48db2a-b624-4936-8a70-3ba23ffd7959.gif)  


## 어려웠던 점.  
~~~
NotificationCenter.default.addObserver(self, selector: #selector(keyboardWillChange(notification:)), name: NSNotification.Name.UIKeyboardWillShow, object: nil)
~~~  
위 코드가 예전엔 잘 작동이 되었는데, 적용이 안되서 찾아보니,  

~~~
UIResponder.keyboardWillShowNotification
~~~
로 바뀌어야 한다는걸 보고 배웠다.  

또 safeArea가 추가된 기종들은 height 값을 그냥 설정하면 safeArea가 포함된 높이 값을 알려줘서 키보드와 textview사이에 빈 공간이 생길수 있다.  
따라서,  
~~~
let height = keyboardFrame.size.height
~~~
를 

~~~
let height = keyboardFrame.size.height - self.view.safeAreaInsets.bottom
~~~
로 바꿔줘야지 키보드 와 textview사이에 빈 공백이 생기지 않는다.  


참고글:<https://stackoverflow.com/questions/52466147/error-with-notification-names-while-converting-code-to-swift-4-2>  
코드주소: <https://github.com/choijaegwon/IOSSimpleResult/tree/main/KaKao_Test>  
출처: <https://www.inflearn.com/course/autolayout-ui_ios> 