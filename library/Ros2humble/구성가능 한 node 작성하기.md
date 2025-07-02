
> 즉 이말은 같은 프로세스에서다른 노드와도 같이 통신가능하도록 만들기 쉽게 하기위한 방법인것 같다. 동적로드

1. 노드를 다이렉트로 상속한 클래스 그리고 메인메소드를 정의한다.

```cpp
namespace palomino
{
    class VincentDriver : public rclcpp::Node
    {
        // ...
    };
}

int main(int argc, char * argv[])
{
    rclcpp::init(argc, argv);
    rclcpp::spin(std::make_shared<palomino::VincentDriver>());
    rclcpp::shutdown();
    return 0;
}
```

2. cmake로 실행 파일을 만든다.

```cmake
# ...
add_executable(vincent_driver src/vincent_driver.cpp)
# ...
install(TARGETS vincent_driver
    DESTINATION lib/${PROJECT_NAME}
)
```

### 코드 업데이트

3. 패키지 의존성 추가하기
```xml
<depend>rclcpp_components</depend>
```
대안으로 build_depend/exec_depend를 사용한다.

```xml
<build_depend>rclcpp_components</build_depend>
<exec_depend>rclcpp_components</exec_depend>
```

4. 클
5. 더이상 메인메서드 필요없다.
너의 메서드는 매크로로 대체가 될 수 있다.
```cpp
#include <rclcpp_components/register_node_macro.hpp>
RCLCPP_COMPONENTS_REGISTER_NODE(palomino::VincentDriver)
```
주의! 대체하려는 메인메서드가 멀티스레드 실행자가 포함될경우 컨테이너노드가 멀티스레드인지 확실이 기록해라.

5. cmake 바꾸기
첫번째로 rclcpp_컴퍼넌트들을 추가한다. 의존성으로서 cmake.Lists.txt에
	
```cmake
find_package(rclcpp_components REQUIRED)
```

두번째 add_excutable을 add_library로 대체
```cmake
add_library(vincent_driver_component src/vincent_driver.cpp)
```
3번째 다른 빌드명령어를 대체한다. 그리고 빌드명령어는 이전대상을 사용하여 새로운 대상에 적용한다.
잊지말아라 `rclcpp_components` in `ament_target_dependencies`. i.e. `ament_target_dependencies(vincent_driver ...)` becomes `ament_target_dependencies(vincent_driver_component "rclcpp_components" ...)`	
	

4번째 새로운 명령어를 추가한다 너의 컴퍼넌트를 선언하기 위해서
```cmake
rclcpp_components_register_node(
    vincent_driver_component
    PLUGIN "palomino::VincentDriver"
    EXECUTABLE vincent_driver
)
```
이전 대상에서 작동하던 CMake의 모든 설치 명령을 변경하여 대신 라이브러리 버전을 설치합니다.
lib/${PROJECT_NAME}에 두 대상을 설치하지 마세요. 라이브러리 설치로 대체하세요.
```cmake
ament_export_targets(export_vincent_driver_component)
install(TARGETS vincent_driver_component
        EXPORT export_vincent_driver_component
        ARCHIVE DESTINATION lib
        LIBRARY DESTINATION lib
        RUNTIME DESTINATION bin
)
```

6. 너의 코드를 실행
See the [[하나의 프로세스에 멀티 노드를 구성하는 방법]] for an in-depth look at composing nodes. The quick and dirty version is that if you had the following in your Python launch file,