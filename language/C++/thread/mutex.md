- 멀티스레드 환경에서 공유 자원에 동시에 접근하지 못하게 막는 동기화 도구 전연변수 포함 포인터 지역변수도 
- 다른스레드가 같은 함수 사용시 lcok부분까지 stop이다 
```cpp
void lock(); // mutex 잠금
void unlock(); // mutex 품
```
- 뮤텍스를 잠근다
- 동일한 쓰레드에서 두번 잠그면 deadlcok 발생
	- 꼭 그렇게 해야 된다면std::recursive_mutex를 사용

### 데드락 해결책(c++ 17)
std::scoped_lock

```cpp
std::mutex sMutex;
std::scope_Lock<std::mutex>(sMutex);
```

- 매개변수로 전달된 뮤텍들을 내포하는 개체를 만듬
-  개체 생성시에 뮤텍스를 잠그고 범위 scope를 벗어날 때  품
- 데드락을 방지
	- c++14의 경우,std::lock_guard를 사용 할수있다 이때는 뮤텍스 하나만 전달가능
	- scope_lock 여러게 전달 가능

