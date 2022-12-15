---
title: Closure Capture List

categories:
  - IOSGrammar
tags:
  - IOS
  - Swift
---

# Closure Capture List

~~~
class Car {
  var totalDrivingDistance = 0.0
  var totalUsedGas = 0.0

  lazy var gasMileage: () -> Double = {
    return self.totalDrivingDistance / self.totalUsedGas
  }

  func drive() {
    self.totalDrivingDistance = 1200.0
    self.totalUsedGas = 73.0
  }

  deinit {
    print("car deinit")
  }
}

var myCar: Car? = Car()
myCar?.drive() // 아직 클로져가 발생하지않았고, 따라서 강한참조사이클은 아직 발생하지 않는다.  
// 따라서 이 시점에서 nil를 할당하면,
myCar = nil // deinit이 실행되면서, 정상적으로 메모리에서 내려가는걸 볼 수 있다.

myCar?.gasMileage() // 강한참조사이클이 발생한다.
myCar = nil // 강한참조사이클이기 때문에 소멸자인 deinit이 실행되지 않는다.
~~~  


## value Type

~~~
var a = 0
var b = 0
let c = { print(a, b) }

a = 1
b = 2
c()
~~~
를 출력해보면
~~~
1 2
~~~
가 출력되는걸 볼 수 있다.  
여기서 클로져의 캡처현상을 사용하면,  

~~~
var a = 0
var b = 0
let c = { [a] in print(a, b) }

a = 1
b = 2
c()
~~~~

출력
~~~
0 2 
~~~
가 출력되는걸 볼 수 있다.  
값형식은 캡처시점에 복사되었던 값이 출력이 된다.  
참조대신 복사본이 출력된다.  

## Reference Type

기본
~~~
{ [weak instanceName, unowned instancename] in 
   statements
}
~~~

활용
~~~
class Car {
  var totalDrivingDistance = 0.0
  var totalUsedGas = 0.0

  lazy var gasMileage: () -> Double = { [weak self] in
    guard let strongSelf = self else { return 0.0}
    return strongSelf.totalDrivingDistance / strongSelf.totalUsedGas
  }

  func drive() {
    self.totalDrivingDistance = 1200.0
    self.totalUsedGas = 73.0
  }

  deinit {
    print("car deinit")
  }
}
~~~
약한 참조는 옵셔널값이라 guard let을 사용하여 언래핑해줘서 사용해야한다.  
이때 아까 
~~~
var myCar: Car? = Car()
myCar?.drive()

myCar?.gasMileage()
myCar = nil
~~~
를 다시한번 실행시켜보면,
~~~
car deinit
~~~
이렇게 메모리에서 내려가서 deinit소멸자가 실행되는걸 볼 수 있다.