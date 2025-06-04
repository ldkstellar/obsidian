##### 새로운 패키지 만들기
```bash
ros2 pkg create --build-type ament_cmake --license Apache-2.0 tutorial_interfaces
```

꼭 ament_cmake 패키지로 사용해야한다.

```cmake
find_package(geometry_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/Num.msg"
  "msg/Sphere.msg"
  "srv/AddThreeInts.srv"
  DEPENDENCIES geometry_msgs # Add packages that above messages depend on, in this case geometry_msgs for Sphere.msg
)
```
 
 interfaces rely on `rosidl_default_generators` for generating language-specific code,
`rosidl_default_runtime` is a runtime or execution-stage dependency, needed to be able to use the interfaces later.

``` xml
<depend>geometry_msgs</depend>
<buildtool_depend>rosidl_default_generators</buildtool_depend>
<exec_depend>rosidl_default_runtime</exec_depend>
<member_of_group>rosidl_interface_packages</member_of_group>
```
The `rosidl_interface_packages` is the name of the dependency group that your package, `tutorial_interfaces`, should be associated with, declared using the `<member_of_group>` tag.

Now you can confirm that your interface creation worked by using the `ros2 interface show` command. The output you see in your terminal should look similar to the following:

``` bash
$ ros2 interface show tutorial_interfaces/msg/Num
int64 num
åå
$ ros2 interface show tutorial_interfaces/msg/Sphere
geometry_msgs/Point center
        float64 x
        float64 y
        float64 z
float64 radius

$ ros2 interface show tutorial_interfaces/srv/AddThreeInts
int64 a
int64 b
int64 c
---
int64 sum
```
