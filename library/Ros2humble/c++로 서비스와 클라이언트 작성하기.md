### 1. 패키지 작성하기

```bash
ros2 pkg create --build-type ament_cmake --license Apache-2.0 cpp_srvcli --dependencies rclcpp example_interfaces
```

### 2.srv파일 만들기
```srv
int64 a
int64 b
---
int64 sum
```
