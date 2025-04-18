CMake에서 제공하는 테스트 도구 모듈이다. CTest 모듈을 사용해서 테스트를 쉽게 정의가 가능하다.

``` cmake
# Ctest 모듈 로드
include(CTest)
```

### BUILD_TESTING

CTest 모듈에서 생성하고 사용하는 변수이다. 변수의 값의 기본 값은 ON이며 OFF인 경우에는 테스트가 활성화 되지 않는다.

``` cmake

# BULILD_TESTING 옵션 정의
option(BUILD_TESTING "Enable build testing." OFF)

# BULID_TESTING 옵션 출력
message(STATUS "Build testing is ${BULID_TESTING}")



```

![[Pasted image 20250325125804.png]]

### add_test
테스트를 정의합니다.

``` cmake
# 테스트 정의
add_test(NAME foo-test COMMAND pass)

# 테스트 정의
add_test(NAME bar-test COMMAND fail)

```

![[Pasted image 20250325134109.png]]

![[Pasted image 20250325134203.png]]