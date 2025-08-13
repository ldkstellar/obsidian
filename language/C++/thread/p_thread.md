
### 1. pthread란?

- POSIX Threads의 약자이다.
- C/C++에서 멀티스레딩을 구현하기 위한 표준 API
- 리눅스, 유닉스 계열 os에서 사용가능
- 스레드 생성, 동기화,종료, 자원 공유 등을 지원
- 라이브러리 링크시 -lpthread 옵션 필요

### 2. pthread의 기본 흐름
1. pthread_create로 새로운 스레드 생성
2. 각 스레드는 독립적인 함수로 실행
3. 필요시 pthread_join으로 스레드 종료 대기
4. 