# List

https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/List.html

- 직접 배열을 다룰 필요가 없다.
- Interface 특성상 경우마다의 구현체로 Swap 가능하다.

## ArrayList

https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/ArrayList.html

- 크기 리사이징 가능한 배열이자 List 인터페이스의 구현체이다.
- 용량과 크기가 정해져있다. (기본 용량: 10)

| Method     | BigO         | Details                                          |
|------------|--------------|--------------------------------------------------|
| add()      | O(1) or O(n) | 일반적으로는 O(1)이지만, 최악의 경우 새로 배열을 생성하고 요소들을 복사해야 한다. |
| get()      | O(1)         | 배열 특징으로, 인덱스를 알고 있다면 바로 값을 가져올 수 있다.             |
| remove()   | O(n)         | 선형 시간. 제거하기 위한 요소를 찾기 위해 전체 배열을 탐색해야 한다.         |
| indexOf()  | O(n)         | 선형 시간. 내부 배열을 반복하며 요소를 확인한다.                     |
| contains() | O(n)         | indexOf() 기반으로 되어 동일한 시간복잡도를 갖는다.                |

## Reference

- https://www.baeldung.com/java-collections-complexity
