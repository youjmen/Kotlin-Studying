# Object

코틀린에서 object 키워드는 클래스를 정의하면서 객체를 생성할 때 사용한다.

인스턴스가 하나 밖에 없는 싱글턴 객체를 만들려면 클래스 이름 앞에 object를 붙이면 싱글턴 객체가 만들어 진다. 싱글턴으로 만든 객체도 다른 클래스나 인스턴스를 상속할 수 있다.

클래스 안에서 선언한 object는 중첩 객체라고 한다. 이 중첩 객체도 인스턴스는 하나고, 기존 object를 붙인 것과 같이 동작한다. 클래스 내의 object는 inner로 선언될 수 없다.


## Companion Object
코틀린 클래스는 정적 멤버가 없다. static 키워드가 없어서 그 대용으로 최상위 함수나 객체 선언을 활용하지만 최상위 함수는 클래스의 private멤버에 접근할 수 없어서 그럴 때 Compainon Object를 사용한다.
* Companion Object는 자신을 둘러싼 모든 클래스의 private 멤버에 접근할 수 있다. 
* Companion Object는 클래스의 객체를 생성하지 않고도 사용할 수 있다.
* Companion Object에서 인터페이스를 구현할 수 있다.

## Anonymous Object
object 키워드로 익명 객체를 만들 수도 있다. 익명 객체는 싱글턴이 아닌 만들때마다 인스턴스가 생긴다.
```kotlin
open class ObjTest {
    open fun doHello(){
        println("안녕하세요")
    }
}
interface Bee{
    fun heyBee()
}
interface Cry{
    fun Cry()
}
fun main(){

    val a = object : ObjTest(),Bee,Cry{
        override fun doHello() {
            println("안녕")
        }

        override fun heyBee() {
            println("꿀벌아 안녕")
        }

        override fun Cry() {
            println("ㅠㅠㅠㅠ")
        }
    }
    a.doHello()
    a.heyBee()
    a.Cry()
}

```
자바의 익명 객체와 달리 코틀린의 익명 객체는 클래스를 확장하면서 인터페이스를 구현할 수 있고, 여러 인터페이스를 구현할 수도 있다.