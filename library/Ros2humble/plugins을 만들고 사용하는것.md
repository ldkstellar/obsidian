pluginlib은 ros패키지에서 로드하고 언로드를 위한 라이브러리 이다.플러그인스는 동적으로 로드할수 있는 라이브러리 이며  **런타임라이브러리**로 부터 로드된다.

pluginlib를 사용하면 클래스를 포함하는 라이브러리에 대해 애플리케이션을 명시적으로 연결할 필요가 없다.
대신 pluginlib는 라이브러리나 클래스 정의가 포함된 헤더파일에 대한 사전 인식 없이도 언제든지 내보낸 클래스를 포함하는 라이브러리를 열 수 있다.

플러그인은 유용하다 확장하거나 변경할때 애플리케이션을 애플리케이션 코드 없이

##### 1. base class 만들기
```bash
ros2 pkg create --build-type ament_cmake --license Apache-2.0 --dependencies pluginlib --node-name area_node polygon_base
```

##### 2. include에 저장
```cpp
#ifndef POLYGON_BASE_REGULAR_POLYGON_HPP
#define POLYGON_BASE_REGULAR_POLYGON_HPP

namespace polygon_base
{
  class RegularPolygon
  {
    public:
      virtual void initialize(double side_length) = 0;
      virtual double area() = 0;
      virtual ~RegularPolygon(){}

    protected:
      RegularPolygon(){}
  };
}  // namespace polygon_base

#endif  // POLYGON_BASE_REGULAR_POLYGON_HPP
// 추상 클래스
```
##### 플러그인 패키지 만들기
```bash
ros2 pkg create --build-type ament_cmake --license Apache-2.0 --dependencies polygon_base pluginlib --library-name polygon_plugins polygon_plugins
```

```cpp
#include <polygon_base/regular_polygon.hpp>
#include <cmath>

namespace polygon_plugins
{
  class Square : public polygon_base::RegularPolygon
  {
    public:
      void initialize(double side_length) override
      {
        side_length_ = side_length;
      }

      double area() override
      {
        return side_length_ * side_length_;
      }

    protected:
      double side_length_;
  };

  class Triangle : public polygon_base::RegularPolygon
  {
    public:
      void initialize(double side_length) override
      {
        side_length_ = side_length;
      }

      double area() override
      {
        return 0.5 * side_length_ * getHeight();
      }

      double getHeight()
      {
        return sqrt((side_length_ * side_length_) - ((side_length_ / 2) * (side_length_ / 2)));
      }

    protected:
      double side_length_;
  };
}

#include <pluginlib/class_list_macros.hpp>

PLUGINLIB_EXPORT_CLASS(polygon_plugins::Square, polygon_base::RegularPolygon)
PLUGINLIB_EXPORT_CLASS(polygon_plugins::Triangle, polygon_base::RegularPolygon)
```

##### plugin 선언 xml
```xml
<library path="polygon_plugins">
  <class type="polygon_plugins::Square" base_class_type="polygon_base::RegularPolygon">
    <description>This is a square plugin.</description>
  </class>
  <class type="polygon_plugins::Triangle" base_class_type="polygon_base::RegularPolygon">
    <description>This is a triangle plugin.</description>
  </class>
</library>
```

##### 플러그인 사용
```cpp
```