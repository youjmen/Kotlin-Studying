# Nested class and Inner class
클래스 안에 다른 클래스를 선언하는 것.

```kotlin

class nestEx {

    class nest1{
     

    }

    inner class inner1{
        fun getBaseClass()= this@nestEx
    }
}

```
inner class에서는 바깥쪽 클래스를 참조 할 수 있지만, nested class에서는 참조할 수 없다.


java에서는 클래스 안에 클래스를 선언하면 코틀린의 inner class가 된다.


kotlin 에서 내부 클래스를 선언하면 java의 static nested class가 된다.


그래서 inner을 붙이지 않으면 상위 클래스를 생성하지 않고도 내부 클래스에 접근할 수 있다.