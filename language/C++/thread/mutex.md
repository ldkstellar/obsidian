```cpp
void lock();
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
-   
