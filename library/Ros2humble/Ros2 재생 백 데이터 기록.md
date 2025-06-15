1. node 실행시킨다.

2. bag files폴더를  만든다.
```bash
mkdir bag_files
cd bag_files
```

3. 토픽을 고른다. 
``` bash
ros2 topic list
```

3. 토픽을 통해 발행된 데이터를 기록한다. ros2 topic echo /turtle1/cmd_vel

4. 토픽을 기록한다.
``` bash
ros2 bag record <topic_name>
```

여러개 토픽들로 기록하기
```bash
ros2 bag record -o subset /turtle1/cmd_vel /turtle1/pose
```
여기서 -o 옵션은 네가 bagfile 이름을 선택 할 수 있다.

5. ros2 bag 실행하기
```bash
ros2 bag play subset
```
6. ros2 bag info
``` bash
ros2 bag info
```