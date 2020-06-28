# Sealed Class

* 이 클래스는 추상 클래스처럼 이 클래스만으로 객체를 생성할 수 없다. 
* 추상 멤버들을 가질수 있다.
* private이 아닌 생성자를 가질 수 없다.
* 기본 open이라 open을 붙이지 않아도 상속할 수 있다.


```kotlin

sealed class Expr //sealed class
class Const(val number: Double) : Expr() //  sealed class의 하위 클래스
class Sum(val e1: Expr, val e2: Expr) : Expr()//  sealed class의 하위 클래스


```
코틀린 컴파일러에선 when을 사용해 타입을 검사할 때 디폴트 분기인 else를 항상 추가해야 하는데 else에 딱히 넣을 값이 없어서 예외를 던진다.

하지만 class에 새로운 하위 클래스를 추가하고 when문에 넣지 않으면 새로 추가한 클래스가 예외 처리되기에 큰 일이 날 수도 있다.


sealed class를 사용하면 when 식에서 디폴트 분기인 else를 추가하지 않아도 된다. when 식에 sealed class의 하위 클래스를 다 정의하지 않으면 컴파일이 되지않아 하위 클래스를 when식에 적어야 하는걸 알수 있기 때문이다.