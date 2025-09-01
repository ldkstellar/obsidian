- 이벤트 개체
- 신호를 받을 때까지 현재 쓰레드의 실행을 멈춤
- notify_one(), notify_all()
	- 멈춰 놓은 스레드 하나 또는 전부를 다시 실행시킴
- wait() , wait_for(), wait_untill()
	- 조건 변수의 조건을 충족시킬때까지 또는 일정 시간 동안 현재 쓰레드의 실행을 멈춤
- std::unique_lock을 사용해야 함

### std::unique_lock
- 기본적으로 scoped lock
- 생성시에 lock을 잠그지 않을 수 있다. (두 번째 매개변수로  std::defer_lock을 전달할 것)
- std::recursive_mutex와 함께 써서 재귀적으로 잠글 수 있음
-  조건 변수에 쓸 수 있는 유일한 lock