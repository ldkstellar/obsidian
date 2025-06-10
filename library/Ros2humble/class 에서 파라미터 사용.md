 노드를 만들 때 때때로 파라미터가 실행할때 설정된게 필요 할 때가 있다.

```cpp
#include <chrono>
#include <functional>
#include <string>
#include <rclcpp/rclcpp.hpp>

using namespace std::chrono_literals;

class MinimalParam : public rclcpp::Node
{
public:
  MinimalParam()
  : Node("minimal_param_node")
  {
    this->declare_parameter("my_parameter", "world");
	// 파라미터 선언 파라미터에 world라는 값을 넣는다.
    timer_ = this->create_wall_timer(
      1000ms, std::bind(&MinimalParam::timer_callback, this));
  }

  void timer_callback()
  {
    std::string my_param = this->get_parameter("my_parameter").as_string();

    RCLCPP_INFO(this->get_logger(), "Hello %s!", my_param.c_str());

    std::vector<rclcpp::Parameter> all_new_parameters{rclcpp::Parameter("my_parameter", "world")};//콜백에서 계속 돌도록
    this->set_parameters(all_new_parameters);
  }

private:
  rclcpp::TimerBase::SharedPtr timer_;
};

int main(int argc, char ** argv)
{
  rclcpp::init(argc, argv);
  rclcpp::spin(std::make_shared<MinimalParam>());
  rclcpp::shutdown();
  return 0;
}
```