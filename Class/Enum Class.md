# Enum Class
* 값을 열거하고, 프로퍼티나 메서드를 정의할 수 있다.

```kotlin

enum class EnumEx(val rgb: Int, val colorName: String) {
    RED(0xFF0000,"빨강"),
    GREEN(0x00FF00,"초록"),
    BLUE(0x0000FF,"파랑")
}
fun main(){
   println(EnumEx.BLUE.colorName)
}
```

* 클래스의 각 열거형 상수들은 객체다.
* 멤버를 정의한다면 열거형 상수들과 구분 짓기 위해 열거형 상수들의 뒤에 세미콜론을 붙인다.
```kotlin
BLUE(0x0000FF,"파랑");
    
val a =5
```