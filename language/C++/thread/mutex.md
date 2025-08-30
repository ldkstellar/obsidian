```cpp
void lock();
```
- 뮤텍스를 잠근다
- 동일한 쓰레드에서 두번 잠그면 deadlcok 발생
	- 꼭 그렇게 해야 된다면std::recursive_mutex를 사용

### 데드락 해결책
std::scoped_lock
```cpp

```