배포는 설치파일을 만드는 것이다.

### InstallRequiredSystemLibraries 모듈
필요한 시스템 런타임 라이브러리를 자동으로 찾아 패키징에 추가

``` cmake
# InstallRequiredSystemLibraries 모듈 로드
include(InstallRequiredSystemLibraries)
```
프로그램이 사용하고 있는 시스템 런타임 라이브러리도 같이 설치 되어야 한다.

### CPack 모듈

설치 프로그램과 소스 패키지를 생성할 수있는 CPackConfig.cmake와 CPackSourceConfig.cmake를 생성한다.

![[Pasted image 20250408142335.png]]

주의해야 할 점: CPack 모듈을 로드하기전에 CPack에서 필요한 변수들을 정의해야 한다.

cpack명령어: 패키징을 실행하는 도구이다.
