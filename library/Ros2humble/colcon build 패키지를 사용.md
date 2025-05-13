  1. workspace 생성하기

```bash
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws
```

루트의 워크스페이스공간에서, run colcon build를 실행한다.colcon 옵션 --symlink-install을 지원한다.
이것은 설치된 파일을 바꿔진다.소스공간에서 파일변경에 의해서 더빠른 반복을 위해