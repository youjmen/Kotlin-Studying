# High-Order function

### 일급 객체란?
코틀린의 함수는 자바와 달리 일급 객체이다. 일급 객체란 무엇일까?
일급 객체는 변수에 할당할 수도 있고, 반환 값이 될 수도 있고, 함수나 생성자의 인자도 될수 있는 것을 일급 객체라고한다.
람다를 사용하면 함수를 값처럼 사용할 수 있어서 코드가 간결해지고 함수를 선언할 필요가 없어진다.

### 고차 함수란?
다른 함수(람다 포함)를 인자로 받거나 함수를 반환하는 함수. 

함수를 인자로 받으려면 함수가 무슨 타입인지 알아야한다. 함수 타입에 대해 알아보자.
```kotlin
fun HighOrderFunc(operation: (Int,Int)->Int) {
    println(operation(1,2))
}
fun main(){
    HighOrderFunc { x, y->x+y}

}


```
위의 코드는 Int형 매개변수를 두개 받고, Int형을 반환하는 람다식을 매개변수로 사용하였다. 그러므로 (Int,Int)->Int가 함수 타입이 되었다.

* 파라미터를 함수로 받을 때도 디폴트 값을 지정할 수 있고, 파라미터에 ?를 붙여서 널이 가능한 파라미터로 만들 수 있다.


