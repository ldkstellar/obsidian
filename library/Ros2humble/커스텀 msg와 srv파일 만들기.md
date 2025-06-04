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
