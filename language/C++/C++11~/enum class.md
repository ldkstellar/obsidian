- c+11에서 제대로 지원
- 정수형으로의 암시적 캐스팅 없음
- 자료형 검사!
- 또한 enum에 할당할 바이트양을 정할 수도 있음

##### enum class용 정수형 명시하기

```cpp
#include<cstdint>
enum class eScoreType: uint8_t
{
	Assignment1,
	Assignment2,
	Assignment3,
	Midterm,
	Final =0x100, //warning

}
```

### enum과 enum class의 차이점
