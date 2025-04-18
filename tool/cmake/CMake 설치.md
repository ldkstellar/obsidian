![[Pasted image 20250403215331.png]]


### 설치를 지원해하는 이유

사용자가 소스 코드에 대해서 신경 쓰지 않아도 된다.
사용자가 빌드 요구 사항과 사용 요구사항에 대해 구분하지 않아도 된다
PATH,LD_LIBRARY_PATH 관리 정책을 따를 수 있다.

### GNUInstallDirs 모듈
GNU 표준 설치 폴더를 정의하는 모듈이다. CMake가 Make로 부터 발전되었기 때문에 이 모듈을 사용해야 한다.
![[Pasted image 20250403220141.png]]

### install

![[Pasted image 20250403235829.png]]

installing-config도 포함해서 export한다는 뜻이다

![[Pasted image 20250404000650.png]]
TYPE INCLUDE는 **CMake의 표준 설치 경로 규칙에 따라 헤더 파일을 CMAKE_INSTALL_INCLUDEDIR로 복사**하라는 의미이다.

• 기본적으로 CMAKE_INSTALL_INCLUDEDIR은 include/ 디렉터리를 가리켜.

• 즉, install(FILES include/foo.h TYPE INCLUDE)는 다음과 동일한 효과를 가짐:

![[Pasted image 20250404001230.png]]
### Prefix란
**Prefix**는 **소프트웨어가 설치될 기본 경로**를 의미해.

