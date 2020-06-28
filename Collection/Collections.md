# Collections
* 대부분의 프로그래밍 언어에 구현되어 있는 자료구조들.
* 코틀린의 컬렉션은 자바 기반으로 만들어 졌다.
* 자바와의 차이는 코틀린에서는 컬렉션 안의 데이터에 접근하는 인터페이스와 컬렉션 안의 데이터를 변경하는 인터페이스를 분리했다는게 다르다.
* 컬렉션 타입에는 대표적으로 list, set, map이 있다.
![컬렉션](https://kotlinlang.org/assets/images/reference/collections-overview/collections-diagram.png)


## List
순서가 정해져있고, 중복된 값을 넣을 수 있음. 순서가 있어 인덱스로 요소에 접근 가능함. 요소가 제거되면 마지막 인덱스에서 부터 한 칸 당겨진다.

## Set
고유한 값을 저장함. 순서가 정해져 있지 않음
## Map

파이썬의 딕셔너리와 유사함. key와 value의 한 쌍으로 이루어진 컬렉션. key는 고유한 값이라 중복될 수 없다. key값으로 value에 접근 가능하다.

### 컬렉션 생성 함수
|컬렉션 타입|읽기 전용 타입|변경 가능 타입|
|---|---|---|
|List|listOf|mutableListOf, arrayListOf|
|set|setOf|mutableSetOf, hashSetOf, linkedSetOf, sortedSetOf|
|Map|mapOf|mutableMapOf, hashMapOf, linkedMapOf, sortedMapOf|

