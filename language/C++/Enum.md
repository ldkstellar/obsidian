>서로 관련된 상수값들을 하나의 이름 아래 묶어서 표현 할 수 있는 자료형

목적
- 가독성 향상
- 타입 안정성

```cpp
enum Direction{
NORTH,
EAST,
SOUTH,
WEST,
};
enum Direction dir = NORTH;// 사용할 때
```

결과적으로 컴파일러가 정수형으로 변환을 해줌