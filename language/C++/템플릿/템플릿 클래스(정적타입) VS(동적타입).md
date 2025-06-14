정적타입이다. 과유 불급 버그나기 십상이다. 

``` cpp
template <class T>

class Vector {

public:

Vector(T, T);

  

private:

T mX;

T mY;

};

  

template <class T>

Vector<T>::Vector(T x, T y) : mX(x), mY(y) {}
```

이런 형태로 사용한다.

### 동적 타입 (런타임에 실행이 된다.)
c++은 any타입이 있다.

c처럼 사용하는 방법은 void*ptr을 사용하는 것이다.
``` c
*(int *)ptr
```
