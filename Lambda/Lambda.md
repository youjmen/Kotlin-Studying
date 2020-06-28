# Lambda


```kotlin
val sum = {x:Int,y:Int->x+y} // 람다식
println(sum(1,2))
// 결과
3
```
* 람다식의 인자가 하나라면 p->.... 가 아닌 it을 사용하여 ->를 사용하지 않고 바로 실행문에 사용할수 있다.
* 인자의 타입을 컴파일러가 추론할수 있는 경우엔 p: Int가 아닌 p 이렇게 타입명시를 생략할 수 있다.
* 메서드의 인자가 람다식 하나라면 maxBy({x:Int,y:Int->x+y})가 아닌
maxBy( ){x:Int,y:Int->x+y} 이렇게 괄호 밖에 람다식을 써도 된다.