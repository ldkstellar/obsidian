Ros2 그래프는 동시에 처리하는  Ros2 원소의 네트워크이다.그것은 모든 실행프로그램을 포괄하고 그것들사이를 연결한다.

Ros에서 각각의 node는 하나의 모듈러의 목적을 책임을 갖는다.즉 서로 서로 데이터를 주고 받는다. 서비스 와 액션 혹은 토픽을 통해서



```bash
ros2 run pakage-name package-name 
ros2 nodelist # 실행중인 node의 list를 출력을 한다.
```


리매핑 
리매핑은 노드의 속성을 재할당이 가능하다. 노드이름 서비스 네임 커스텀 값 

``` bash
ros2 run turtlesim turtlesim_node --ros-args --remap __node:=my_turtle
```

###### 요약
노드는 근본적인 ros2 엘레먼트인다. 그리고 그것은  단일,모듈 목적의 역할을 한다. 로봇 시스템에서