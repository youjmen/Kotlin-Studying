# Data Class
* 데이터를 저장하는 역할만을 수행하는 클래스
* 상속이 불가능함
* toString, equals, hashCode, copy 메서드가 자동으로 구현됨
* 데이터 클래스는 abstract, open, sealed, 내부 클래스가 될 수 없다.

## toString()
일반 클래스에서 toString을 하면 hashcode가 나오는데 data class 에서 toString을 하면 생성자에 있는 속성들이 출력된다.


* data class: Ex(name=dasfasdf, age=5)
* 일반 클래스 :dataClassPractice.Ex2@6e0be858


그래서 일반 클래스에서 한것처럼 불편하게 멤버에 접근해야만 정보를 알수 있는게 아닌 toString만 하면 정보를 알수 있어서 logging등을 하는데 편하다.
인스턴스를 문자열로 표현하는 것이다.
override해서 인스턴스를 어떻게 출력할지 결정할 수 있다.

## equals()
동등한 객체인지 검사하고 true, false 반환

```kotlin
data class Ex(val name : String, val age: Int) {


}
class Ex2(name: String){



}
fun main(){

    val a =Ex("나",4)
    val b =Ex("나",4)
    val c =Ex2("나")
    val d =Ex2("나")
    println(a==b)
    println(a.equals(b))
    println(c==d)
    println(c.equals(d))

}

//실행 결과
true
true
false
false
```
data class에서는 속성 값이 같다면 모두 true를 출력한다.
코틀린에서는 ==이 내부적으로 equals()를 호출한다.

## hashCode()
equals만 선언하면 hashcode를 선언하지 않았다고 노랗게 밑줄이 생긴다.
그 이유는 equals가 객체를 검사할 때 두 객체의 hashcode가 같은지 다른지로 true, false를 반환하기 때문이다
```kotlin 
   println(a.hashCode())
    println(b.hashCode())
    println(c.hashCode())
    println(d.hashCode())
// 실행 결과
1401452
1401452
1846274136
1639705018

```
위의 equals()와 동일한 코드에서 상단의 코드만 추가 했는데 결과가 이렇다.
## copy()
코틀린에서는 data class의 프로퍼티를 immutable로 하길 권장한다.
하지만 immutable로 사용하기에는 조금 어려운 감이 있다. 

그래서 코틀린에서는 copy()라는 메서드로 객체를 복사(얕은 복사)하면서 일부 프로퍼티를 바꿀수 있게 해준다. copy()로 복사된 객체는 원본 객체와는 다른 생명주기를 가진다.