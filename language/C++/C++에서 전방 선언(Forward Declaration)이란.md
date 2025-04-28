전방 선언(Forward Declaration)은 클래스 도는 함수의 선언만 미리 알려주고 실제 정의는 나중에 제공하는 기법
-  헤더 파일 간의 의존성을 줄여서 컴파일 시간을 단축
-  불필요한 include를 최소화하여 컴파일 속도를 향상시킬 수 있다.


A.h

```cpp
#ifndef A_H
#define A_H

class B;  // 전방 선언 (B의 정의를 여기서는 포함하지 않음)

class A {
private:
    B* b;  // 포인터로 사용 -> 전방 선언 가능
public:
    A();
    ~A();
    void setB(B* newB);
};

#endif
```

구현 파일

a.cpp
``` cpp
#include "A.h"
#include "B.h"  // 실제 구현이 필요하므로 여기서 포함

A::A() : b(nullptr) {}
A::~A() = default;
void A::setB(B* newB) { b = newB; }
```
