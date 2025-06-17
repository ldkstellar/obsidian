> 즉 이말은 다른 노드와도 같이 통신가능하도록 만들기 쉽게 하기위한 방법인것 같다.

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

3. 패키지 의존성 추가하기
```xml
<depend>rclcpp_components</depend>
```
대안으로 build_depend/exec_depend를 사용한다.

```xml
<build_depend>rclcpp_components</build_depend>
<exec_depend>rclcpp_components</exec_depend>
```

4. 더이상 메인메서드 필요없다.
너의 메서드는 매크로로 대체가 될 수 있다.
```cpp
#include <rclcpp_components/register_node_macro.hpp>
RCLCPP_COMPONENTS_REGISTER_NODE(palomino::VincentDriver)
```
	주의! 대체하려는 메인메서드가 멀티스레드 실행자가 포함될경우 컨테이너노드가 멀티스레드인지 확실이 기록해라
	

