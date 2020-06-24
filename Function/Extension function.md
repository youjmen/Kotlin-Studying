# 확장 함수

코틀린은 상속 없이 확장 함수를 이용하여 클래스를 확장 할 수 있다.

```kotlin
//확장 함수
 class Test {

}
fun main(){


    Test().swap()
    "wow".printString() // "wow"가 수신 객체, 호출되는 값
}
fun Test.swap(){
    print("asdf")
}
fun String.printString(){
    print(this) // this는 수신 객체
}
```
확장할 클래스의 이름뒤에 .함수이름을 쓰고 작성하면 확장이 그 클래스에 대한 확장 함수가 생긴다.


* 확장 함수에서는 클래스의 private멤버와 protected 멤버에 접근할 수 없어 캡슐화를 깨지 않는다. 
* 확장 함수는 정적 자바 메소드로 컴파일 되어 override할 수 없다.
* 확장 함수와 동일한 함수 명이 클래스에 있다면 그 클래스 내부의 함수가 먼저 우선된다.
* 위의 특징들 덕분에 확장 함수는 그들이 확장하는 클래스를 실제로 확장하는 것이 아니라는 것을 알 수 있다. 그 클래스는 실질적으로 변한 것이 없다.


## 확장 프로퍼티

확장 프로퍼티도 확장 함수와 같이 수신 객체 클래스명 뒤에 .프로퍼티 이름으로 선언한다. 확장 프로퍼티는 뒷받침하는 필드가 없어서 기본 게터가 없다. 그래서 게터를 정의해줘야하고, 초기화 코드를 담을 장소가 없어서 초기화 코드도 쓸 수 없다.
```kotlin

val String.lastChar : Char
    get ()= get(length-1)// 프로퍼티 게터
    set(value : Char){
        this.setCharAt(length-1,value)// 프로퍼티 세터
    }

```