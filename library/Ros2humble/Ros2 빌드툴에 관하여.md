### XML과 Cmake의 관계
- XML: 어떤패키지가 필요한지 찾을수 있도록 도와주는 역할
- Cmake: 코드 생성, 빌드
### XML태그의 기본구조
`<export>` 태그는 ros2에서 특정 빌드시스템이나 도구에 대한 정보를 제공하는 용도로 사용이 된다.


### ament와 ament_cmake의 관계
- ament: Ros2의 빌드 시스템 전체 이름이다.
- ament_cmake: ament의 하위 모듈로, CMake를 사용하는 패키지를 빌드하기 위한 플러그인 역할