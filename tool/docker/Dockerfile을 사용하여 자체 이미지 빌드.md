```dockerfile
FROM node:latest

# 하위 명령어 디렉토리지정

WORKDIR /app

# 패키지json을 -> /app

COPY package.json .

  

# docker runs시 실행할 명령어

RUN npm install

# 나머지 모든 디렉토리 파일들 옮긴다. 뒤에있는 레이어만 다시 실행된다.

COPY . .

  

# 3000 port 열기

EXPOSE 3000

  

# 컨테이너 시작시에 실행하는 명령어

CMD [ "node","app.mjs" ]
```
