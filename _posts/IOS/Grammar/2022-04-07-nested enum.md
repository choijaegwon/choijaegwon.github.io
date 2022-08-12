---
title: "nested enum"

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

## nested enum  

~~~ 
import UIKit

// 이넘안에 이넘을 중첩으로 두어 사용이 가능하다.
enum MyFavoriteFood {
    case chocolate //초콜렛
    case porkBelly //삼겹살
    case pasta(ItalyPasta) //파스타
    // 이태리 파스타
    enum ItalyPasta {
        case carbonara //까르보나라
        case tomato //토마토
        case rose //로제
    }
}

class ViewController: UIViewController {
    override func viewDidLoad() {
        super.viewDidLoad()
        let favoriteType = MyFavoriteFood.pasta(.carbonara)
        let favoriteFoodType = MyFavoriteFood.chocolate
        switch favoriteType {
            case .pasta(let pastaType):
                print("pastaType: \(pastaType)")
            switch pastaType {
            case .carbonara:
                print("까르보나라")
            case .tomato:
                print("토마토")
            case .rose:
                print("로제")
            }
        default: break
        }
    }
}
~~~

