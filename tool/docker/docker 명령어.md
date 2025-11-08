
#### 기본기 3가지
1. run - 새 컨테이너를 생성하고 실행한다.
2.  start - 이미 생성된 컨테이너를 실행한다.
3. exec - 이미 실행중인 컨테이너 안에서 명령어 실행

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

docker run -d
detach # 모드에서는  로그를 확인할수 없다. 다른 명령어를 사용가능 하다.즉 백그라운드에서 실행하는 것이다.

docker logs #컨테이너_이름해당 컨테이너의 로그를 다 출력한다. 

docker stop 컨테이너 이름
docker run --name 이미지이름 | 이미지id

docker run -it # interactive + t

docker run -p 3000:80 # 외부 포트 내부 포트 연결

docker start -i -a

docker rmi 이미지id # 이미지 삭제

docker images inspect 이미
docker image prune #로컬 이미지 전체 삭제
```

##### 도커컨테이너 관련 명령어

```bash
docker rm 컨테이너이름 # 컨테이너 삭제
docker run -it --name my_container ubuntu /bin/bash # 컨테이너를 등록하고 실행
docker start -it --name mu_container ubuntu /bin/zsh # 컨테이너 실행중에 실행
```