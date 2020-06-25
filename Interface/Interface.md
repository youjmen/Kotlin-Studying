# Interface
자바와 달리 코틀린 인터페이스는 추상 메서드를 선언만 하는 게 아니라 구현까지 할 수 있다.

## 인터페이스 사용 이유?
느슨한 결합성을 위해서

* 인터페이스를 구현하는 클래스는 무조건 인터페이스의 추상 메서드를 구현해야 한다.
* 프로퍼티, 디폴트 메서드 구현을 포함할 수 있다.
* 인터페이스는 생성자를 가질 수 없다.
* 인터페이스에서 메서드를 구현해놨다면 그 메서드를 구현하지 않아도 된다.
* 구현하지 않은 추상 메서드는 무조건 클래스에서 구현해야한다.
```kotlin
//인터페이스 예제
interface SomeInterface{
    val a : Int

    val b : Int
    fun doHello(){
        print("hello")
    }
}
class SomeClient: SomeInterface{
   fun doSomething(){
        print("hey ")
    }

    override var a: Int = 0


    override val b: Int
        get() {
            return 5
        }

}
fun main(){
    val foo =SomeClient()
    foo.a =5
    println(foo.b)
    println(foo.a)
}
```
### 인터페이스 프로퍼티
* 구현 클래스에서 무조건 구현해야 한다.
* 인터페이스에서 val로 선언한걸 var로 오버라이드할 수 있다.
* 커스텀 게터와 세터를 사용할 수 있다.