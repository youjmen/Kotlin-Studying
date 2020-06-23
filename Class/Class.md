# 클래스

프로퍼티 : 자바에서는 필드와 접근자(getter, setter)를 한데 묶어 프로퍼티라고 한다. 코틀린에서는 이 프로퍼티가 언어 기본 기능이라 getter setter가 필요 없어졌다.

```kotlin
class Ex {
    var sample =0
}
fun main(){

    val a= Ex()
    val b = a.sample
    a.sample=5
}
```
저렇게 클래스의 필드를 getter, setter 없이 막 사용하는 것 같지만 코틀린에서는 인스턴스.필드 로 사용하여도 getter와 setter가 자동으로 호출된다.  

그러면 코틀린 클래스에서 private 프로퍼티를 선언하면 어떻게 될까?
```kotlin

class Ex {
    private var sample=0

}

class Ex2 {
    var sample = 0
}
fun main(){

    val ex= Ex()
    val b = ex.sample // 사용할 수 없음
    ex.sample=5 // 사용할 수 없음

    val ex2 = Ex2()
    val test = ex2.sample // 사용할 수 있음
    ex2.sample=5 // 사용할 수 없음
}

```
위의 클래스 코드들을 JVM 바이트 코드로 변환한 후 디컴파일을 하면 자바 코드로 변하는데 변한 코드는 이러하다.
```java
public final class Ex {
   private int sample;
}


public final class Ex2 {
   private int sample;

   public final int getSample() {
      return this.sample;
   }

   public final void setSample(int var1) {
      this.sample = var1;
   }
}
```
그래서 코틀린 클래스에서의 private 프로퍼티는 getter와 setter가 없어서 클래스 내에서만 사용가능하다.

기본적으로 코틀린 클래스 내의 프로퍼티는 private으로 되어있다는 것도 알 수 있다.



