---
title: " 'windows' was deprecated in iOS 15.0: Use UIWindowScene.windows on a relevant window scene instead "

categories:
  - IOSUIkit
tags:
  - IOS
  - Swift
  - Dispatch Queue
---

# 'windows' was deprecated in iOS 15.0: Use UIWindowScene.windows on a relevant window scene instead
오류 해결하기
~~~
guard let window = UIApplication.shared.windows.first(whrer: { $0.isKeyWindow }) else { return }
guard let (사용할변수) = window.rootViewController as? MainTabController else { return }
~~~
를
~~~
let scenes = UIApplication.shared.connectedScenes
let windowScene = scenes.first as? UIWindowScene
guard let window = windowScene?.windows.first(where: { $0.isKeyWindow }) else { return }
guard let (사용할변수) = window.rootViewController as? MainTabController else { return }
~~~
로 바꾸어 사용할 수 있다.