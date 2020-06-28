# Delegation

위임은 자신이 구현해야하는 메서드를 다른 객체에 떠넘기는 것이다.


하위 클래스가 상위 클래스의 메서드를 오버라이드 하면 상위 클래스의 메서드에 의존적이라 상위 클래스의 변경에 민감하다. 

그렇기에 상속을 허용하지 않는 클래스들이 있는데 이 상속이 안되는 클래스를 확장해야 하거나 클래스 간의 loose coupling을 위하여 데코레이터 패턴을 사용할 수도 있지만 코드의 수가 길기 때문에 위임을 사용한다.

위임을 사용하려면 다른 언어에선 boilerplate 코드를 많이 작성해야 했는데 kotlin 에서는 by 키워드로 위임을 간편하게 할 수 있다.

```kotlin
interface Base {
    fun print()
}

class BaseImpl(val x: Int) : Base {
    override fun print() { print(x) }
}

class Derived(b: Base) : Base by b

fun main() {
    val b = BaseImpl(10)
    Derived(b).print()
}
```
원래라면 Derived 클래스가 Base 인터페이스의 print를 구현해야하지만 생성자의 매개변수로 받은 BaseImpl에 책임을 위임하여 구현하지 않고도 print를 사용할 수 있게 되었다.