1. ABI 영향을 주는 전역 설정을 한다.
2. 타겟을 정의 한다.
3. 타겟에서 공개해야 할 것 과 하지 않을 것을 나눈다.
4. 타겟의 프로퍼티를 설정한다.

``` cmake
# 타겟을 컴파일할 때 사용할 인클루드 디렉토리를 지정
target_include_directories(foo PUBLIC
	include
	PRIVATE
	src
)

# 타겟을 링킹할 때 필요한 타겟이나 라이브러리를 지정
target_link_libraries(foo
PUBLIC
	abc
PRIVATE
	xyz
)
```

공개와 비공개를 구분해서 설정 한다.
지양해야 되는 설정

``` cmake
# 모든 타겟에 영향을 주는 컴파일 디파인을 지정
include_directories(include)

# 모든 타겟에 영향을 주는 컴파일 디파인을 지정
add_definitions(NOMIMAX)

# 모든 타겟이 링킹할 타겟이나 라이브러리를 지정
link_libraries(abc xyz)

# ABI에 영향을 주는 컴파일 옵션을 타겟을 지정
target_compile_options(foo PRIVATE -no-rtti -std=c++0x)

# 타겟 밖의 디렉토리를 타겟의 인클루드 디렉토리로 지정
target_include_directories(foo PUBLIC ../bar/include)

```

결론은 전역으로 설정되는 명령어를 지양해야 되는 것이다.

### 시나리오 과정

![[Pasted image 20250227221942.png]]

CMake 실행시 최상단에 CMakeLists.txt 파일이 제일 먼저 실행이 된다. 모던에서 영향을 주는 것은 전역으로 설정을 한다.


