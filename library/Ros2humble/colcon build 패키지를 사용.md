  1. workspace 생성하기

```bash
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws
```

루트의 워크스페이스공간에서, run colcon build를 실행한다.colcon 옵션 --symlink-install을 지원한다.
이것은 설치된 파일을 바꿔진다.소스공간에서 파일변경에 의해서 더빠른 반복을 위해

```bash
colcon build --symlink-install
```

2. 실행 테스트
빌드 잘되었는지 test하는것이다.

3. 소스 환경
colcon으로 지금까지 성공적으로 빌드를 완료 했을 때
결과물은 install 디렉토리에 있을 예정이다.너가 설치된 실행팔일 이랑 라이브러리를들 추가할때는  너는 라경로와 라이브러리경로를 추가해야한다.  콜콘이 만든다 bash files들을 설치폴더를 환경을 설정을 도와주는 파일을  

