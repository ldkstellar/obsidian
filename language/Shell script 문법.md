
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

##### 문자열 
```bash
"$variable" # 줄바꿈하지 않고 계속이어짐
$variable 줄바꿈
```
##### 예약변수 및 환경변수

```bash
HOME # 사용자 홈 디렉토리

PATH # 실행 파일을 찾을 디렉토리 경로

PWD # 현재 경로

HOSTNAME

USER #사용자 이름

USERNAME #사용자 이름

LOGNAME #로그인한 사용자

```

##### 위치 매개변수

- 스크립트 수행시 함께 넘어오는 파라미터를 의미한다.

```bash

$0 # 실행파일

$1 # 1번파미터

$2 # 2번 파라미터

${10} # 10번 파라미터

$@ # 전체 파라미터

$* # 전체 파라미터 

"$@" # 개별 문자열로 취급

"$*" # 하나의 문자열 취급
```

##### for문
```bash
for language in $@; do

```

