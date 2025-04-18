fetchContent는 CMake에서 제공하는 모듈이다.
지정된 컨텐츠를 어떻게 가져올지 선언한다. GIT , URL , SVN 등 다양한 방법을 제공한다.
### include 
파일에 작성된 Cmake 코드를 실행하거나 모듈을 불러온다.

``` cpp
# 모듈 로드
include(CheckIncludeFileCXX)

# 파일에 작성된 Cmake 코드를 실행하거나 모듈을 불러온다.
check_include_file_cxx("filesystem" CXX_FILESYSTEM_HAVE_HEADER) 

# 파일이 없는 경우 메세지 출력 
if (NOT CXX_FILESYSTEM_HAVE_HEADER)
	message(STATUS "Oh no! can't use filesystem!")
endif()

```

### Fetch Content
```cpp
FetchContent_MakeAVailable(spdlog poco)

```

선언된 컨텐츠를 프로젝트에서 사용할 수 있도록 준비한다.

m5sum을 사용하여 해시값을 구할 수 있다.