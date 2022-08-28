# Lists
- [Java 11 List API Document](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/List.html)
- [Time Complexity of Java Collections](https://www.baeldung.com/java-collections-complexity)

## ArrayList

https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/util/ArrayList.html

- List 인터페이스 구현체이자 동적으로 크기 변경이 가능한 배열을 내포한다.
 

| Method     | BigO         | Details                                          |
|------------|--------------|--------------------------------------------------|
| add()      | O(1) or O(n) | 일반적으로는 O(1)이지만, 최악의 경우 새로 배열을 생성하고 요소들을 복사해야 한다. |
| get()      | O(1)         | 배열 특성상, 인덱스가 있으면 빠르게 값을 가져올 수 있다.                |
| remove()   | O(n)         | 선형 시간. 제거하기 위한 요소를 찾기 위해 전체 배열을 탐색해야 한다.         |
| indexOf()  | O(n)         | 선형 시간. 내부 배열을 반복하며 요소를 확인한다.                     |
| contains() | O(n)         | indexOf() 기반으로 되어 동일한 시간복잡도를 갖는다.                |

### add()
- 리스트의 맨 마지막에 요소를 추가한다.
- 지정된 크기(기본:10)를 넘으면, 용량을 증가시킨 배열에 옮겨담는 작업을 수행한다. 

```java
// add() 내부 배열 리사이징, 복사 수행 과정
private void grow(int minCapacity) {
        // overflow-conscious code
        int oldCapacity = elementData.length;
        int newCapacity = oldCapacity + (oldCapacity >> 1);
        if (newCapacity - minCapacity < 0)
            newCapacity = minCapacity;
        if (newCapacity - MAX_ARRAY_SIZE > 0)
            newCapacity = hugeCapacity(minCapacity);
        // minCapacity is usually close to size, so this is a win:
        elementData = Arrays.copyOf(elementData, newCapacity);
    }
```

### remove()
- 지정된 위치의 요소를 제거하고 배열을 복사한 뒤, 마지막 요소를 제거한다.

```java
public E remove(int index) {
        rangeCheck(index);

        modCount++;
        E oldValue = elementData(index);

        int numMoved = size - index - 1;
        if (numMoved > 0)
            System.arraycopy(elementData, index+1, elementData, index,
                             numMoved);
        elementData[--size] = null; // clear to let GC do its work

        return oldValue;
    }
```
