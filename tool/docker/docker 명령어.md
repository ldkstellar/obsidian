##### 도커파일 관련 명령어

```bash
docker build --name 이미지이름  .
```
##### 도커 이미지관련 명령어

```bash
docker images # 도커이미지들 출력
docker ps -a 명령어를 사용해서 
중지된 컨테이너를 확인이 가능하다.

docker run은 터미널 차단
# 컨테이너는 포어그라운드에서 실행중이다.
# 즉, 터미널에서 기록이 나온다.

detach # 모드에서는  로그를 확인할수 없다. 다른 명령어를 사용가능 하다.

docker logs #컨테이너_이름해당 컨테이너의 로그를 다 출력한다. 

docker run --name 이미지이름 | 이미지id

docker run -it # interactive + t

docker start -i -a

docker rmi 이미지id # 이미지 삭제

docker image prune #로컬 이미지 전체 삭제
```

##### 도커컨테이너 관련 명령어

```bash
docker rm 컨테이너이름 # 컨테이너 삭제
```