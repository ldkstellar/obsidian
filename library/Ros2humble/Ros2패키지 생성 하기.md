[[Ros2 작업저장소 만들기]]
##### 1. 패키지 생성 명령어

``` bash

ros2 pkg create --build-type ament_cmake --license Apache-2.0 <package_name> # 패키지 이름

ros2 pkg create --build-type ament_cmake --license Apache-2.0 --node-name my_node my_package # 노드네임까지 설정이 가능하다.
```
노드네임이 cpp파일이다.
##### 2. 패키지를 빌드하기 

```bash
colcon build
colcon build --packages-select my_package
```

##### 3. 설치파일 소스
```bash
source install/local_setup.zsh

```

##### 커스터마이즈 package.xml
```xml
<?xml version="1.0"?>
<?xml-model
   href="http://download.ros.org/schema/package_format3.xsd"
   schematypens="http://www.w3.org/2001/XMLSchema"?>
<package format="3">
 <name>my_package</name>
 <version>0.0.0</version>
 <description>TODO: Package description</description> <?패키지에 대한 요약 ?>
 <maintainer email="user@todo.todo">user</maintainer>
 <license>TODO: License declaration</license>

 <buildtool_depend>ament_cmake</buildtool_depend>

 <test_depend>ament_lint_auto</test_depend>
 <test_depend>ament_lint_common</test_depend>

 <export>
   <build_type>ament_cmake</build_type>
 </export>
</package>
```
