---
title: "기본 문법(Deinitializtion)"

categories:
  - UIkit
tags:
  - IOS
  - Swift
  - Deinitializtion
---

## Deinitializtion(메모리 해제)
간단한예제는
~~~
var a: Int? = 10
a = nil
~~~
출력하면
~~~
10
nil
~~~
이다. 사용을 안할때 nul로 적어주면 된다.  
다른큰 예제를 보자.  
~~~
class Game {
  var score = 0
  var name = ""
  var round: Round?

  init(){
    print("game init")
  }
  deinit{
    print("gaem deinit")
  }

}

class Round {
  var gameInfo = Game?
  var lastRound = 10
  var roundTime = 20
}

var game: Game? = Game()
game = nil
~~~
출력하면
~~~
game init
game deinit
~~~
게임 init이 먼저 나오고, game = nil하고 난후에 deinit이 나오는걸 볼 수 있다.
이렇게 메모리에서 내렸을때 deinit메서드가 활성화 된다.  
~~~
class Game {
  var score = 0
  var name = ""
  var round: Round?

  init(){
    print("game init")
  }
  deinit{
    print("gaem deinit")
  }

}

class Round {
  var gameInfo = Game?
  var lastRound = 10
  var roundTime = 20
}

var game: Game? = Game()
var round: Round? = Round()

round?.gameInfo = game
game?.round = round

game = nil
~~~
출력하면
~~~
game init
~~~
nil을 해도 deinit이 안된다.즉 이런 방식으로 서로 참조를 하면 메모리 누수가 일어난다.  

## 강제하는 방법
~~~
class Game {
  var score = 0
  var name = ""
  var round: Round?

  init(){
    print("game init")
  }
  deinit{
    print("gaem deinit")
  }

}

class Round {
  weak var gameInfo = Game?
  var lastRound = 10
  var roundTime = 20
  deinit {
    print("round deinit")
  }
}

var game: Game? = Game()
var round: Round? = Round()

round?.gameInfo = game
game?.round = round

game = nil
round = nil
~~~
Game은 Round가 없어도 되지만,  
Round는 Game이 없으면 존재자체가 없다.  
따라서 위코드 처럼 Round 앞에 weak를 붙여주면, Game이 없으면 자기도 같이 없애겠다는 의미이다.  
출력하면
~~~
game init
game deinit
round deinit
~~~
이렇게 deinit이 된다.