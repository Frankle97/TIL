# Array

```java
class Array {
    public static void main(String[] args) {
        int[] intArray = new int[4]; // 크기가 4로 고정

        // 0번째의 메모리 주소값을 12라고 가정한다.
        intArray[0] = 13;   // @12 (12 + (4*0))
        intArray[1] = 21;   // @14 (12 + (4*1))
        intArray[2] = 5;    // @16 (12 + (4*2))
        intArray[3] = -41;  // @18 (12 + (4*3))
    }
}
```

- 한번 생성한 뒤에는 크기 변경이 불가능하다.
- 인덱스는 0부터 시작한다.
- 연속된 블록으로 메모리에 저장된다.
- 인덱스를 알고 있다면, 요소를 빠르게 찾을 수 있다.
