1. Configure 단계
	- CMakeLists.txt 분석한다.
	- CMakeCache.txt를 생성한다.
2. Generate 단계
	-  configure 단계에서 생성된 파일들을 사용해 Native Build System 파일을 생성한다.

## 주의점

CMakeCache.txt에 정의된 변수를 사용하기 때문에 CMakeCache.txt가 갱신되지 않는다면 원치 않는 Native Build System 파일이 생성될 수 있다.

CMakeCache.txt는 문제의 근원이다.
- --fresh = Configure a fresh build tree, removing any existing cache file.
- CMakeCache.txt를 삭제한다.


