### 툴 체인은  관리한다. nvm 과 비슷 하다. rustup

Cargo는 빌드 시스템이고 패키지 매니저이다. npm이랑 동일함

``` zsh
cargo new project-Name # 새로운 프로젝트 생성
cargo build 
npm run
```

compiler는 rustc이다.

```json
{

"version": "2.0.0",

"tasks": [

{

"label": "rustc",

"type": "shell",

"command": "rustc",

"args": [

"${file}",// 빌드타겟  파일 

"-o",

"${fileDirname}/${fileBasenameNoExtension}.out"// 빌드된 파일 형태

],

"problemMatcher": [],

"group": {

"kind": "build",

"isDefault": true

}

}

]

}

```

rust-analysis 는 c++ extension이라고 보면된다. 자동으로  cargo check를 해준다.이게 컴파일러가 실시간으로 컴파일
