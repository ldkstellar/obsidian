1. 서버 pc에서 openssh-server를 받고 실행해 준다.

```bash
sudo apt install openssh-server
sudo systemctl start ssh
sudo systemctl enable ssh
```

`systemctl` 는 `systemd`를 통해 실행되는 **백그라운드 서비스를 관리하는 명령어입니다.**  
`start ssh`는 ssh 서비스를 시작하는 명령, `enable ssh`는 서버 PC 부팅 시 자동으로 ssh 서비스를 실행하도록 하는 명령입니다.

