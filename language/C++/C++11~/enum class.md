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

| 특징     | enum                                      | enum class                       |
| ------ | ----------------------------------------- | -------------------------------- |
| 스코프    | 전역 네임스페이스                                 | 열거자 내부에만 존재 -> Color::RED        |
| 타입 안정성 | 기본형(int)으로 아묵 변환 가능 -> 다른 숫자 타입과 혼용시 에러안남 | 암묵 변환 불가 -> 반드시 명시적 캐스팅 필요       |
| 기본자료형  | 구현에 따라 보통 int                             | 명시 안 하면 기본 int이지만, 원하는 자료형 지정 가능 |
