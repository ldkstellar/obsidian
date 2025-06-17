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