
##### 쉘스크립트 실행
- sh 명령어를 사용
- chmod +x명령어를 이용: 실행권한을 준
- echo를 사용

```bash
#!/bin/bash

 language="Korean" # 변수 설정
 echo "Ican speak $language" #변수 출력
 mkdir $language # 디렉토라 생성
 
```

##### 함수 생성

```bash
function print(){
echo $1 # 함수 파라미터 1
echo $2 # 함수 파라미터 2
}
print "I can speak korean" "helloworld"
```

##### 전역변수
그냥 이름 쓰면 전역변수

##### 지역변수
```bash
function learn(){
	local learn="english"
	echo $learn
}
```