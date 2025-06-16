Null 문제
- Null을 쓰면 가끔 뭔가 광장히 이상한 일이 벌어짐
```cpp
// Class.h
float GetScore(const char* name);
float GetScore(int id);

// Main.cpp
Class* myclass = new Class("COMP3100");
//
int score = myclass->GetScore(NULL);
//어떤 함수가 호출이 될까?
```
결론 int형 파라미터인 함수가 호출이 된다.

##### Null vs nullptr
숫자 vs null포인터 상수
