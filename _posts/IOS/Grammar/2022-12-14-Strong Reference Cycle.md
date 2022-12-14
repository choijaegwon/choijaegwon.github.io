---
title: Strong Reference Cycle

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Strong Reference Cycle

~~~
class Person {
  var name = "John Doe"
  var car: Car?

  deinit {
    print("person deinit")
  }
}

class Car {
  var model: String
  var lessee: Person?

  init(model: String) {
    self.model = model
  }

  deinit {
    print("car deinit")
  }
}

var person: Person? = Person()
var rentedcar: Car? = Car(model: "Porsche") // 아직까진 Person과 rentedCar 둘다 하나씩 참조하고 있다

// 하지만
person?.car = rentedCar // Person인스턴스가 Car인스턴스를 가르켜 Person은 1참조 Car는 참조가 2개가 된다.
rentedCar?.lessee = person // Person인스턴스가2 Car인스턴스가2 카운팅이된다.

person = nil // Person인스턴스가1 Car인스턴스가 2 카운팅된다.
rentedCar = nil // Person인스턴스가1 Car인스턴스가 1 카운팅이 된다.
~~~  

이떄 둘다 nil을 해줘가지고, 두 인스턴스에 접근할 방법이 없다.  
따라서 참조카운트 때문에 인스턴스를 해결하지 못하는 이 경우가 바로 강한참조 사이클이다.  
이를 해결을 하려면 이렇게  
~~~
class Person {
  var name = "John Doe"
  var car: Car?

  deinit {
    print("person deinit")
  }
}

class Car {
  var model: String
  weak var lessee: Person?

  init(model: String) {
    self.model = model
  }

  deinit {
    print("car deinit")
  }
}
~~~
weak키워드를 붙여주면된다.  
이러면 Person?를 참조하지만 소유하진 않아진다. 그래서 
다시  
~~~

var person: Person? = Person()
var rentedCar: Car? = Car(model: "Poresche")

person?.car = rentedCar
rented?.lessee = person

person = nil // 이때 weak를 사용해서 약한 참조를 해줬기때문에 Person인스턴스 카운트는 0이되면서  deinit이 사용되며 메모리에서 종료된다
// 그러면서 Car인스턴스카운터를 자동으로 1 줄여준다. 
~~~