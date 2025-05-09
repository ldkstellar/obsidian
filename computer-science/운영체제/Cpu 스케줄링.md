
##### FcFs(First-come First-served)

| process | 금번 cpu 사용시간 |
| ------- | ----------- |
| p1      | 24          |
| p2      | 3           |
| p3      | 3           |
waiting time: p1: 0 p2: 24 p3: 27
average wating time: (0 + 24 +27)/3 =17

##### SJF (shortest-Job-First)
가장 짧은 프로세스를 제일 먼저 스케줄링

| 프로세스 | 도착시간 | 실행 시간 (Burst Time) |
| ---- | ---- | ------------------ |
| P1   | 0    | 6                  |
| P2   | 1    | 8                  |
| P3   | 2    | 7                  |
| P4   | 3    | 3                  |
도착시간 고려 -> 실행시간 짧은 순으로 실행중에 프로세스가 도착해야한다.
P1-> P4-> P3-> P2

##### Round Robin [RR]
각 프로세스는 동일 크기의 cpu 할당시간을 가진다.
할당시간이 끝나면 인터럽트 발생한다. 프로세스 cpu를 빼앗기고
cpu queue의 제일 뒤에 줄을 선다.
대기시간이 cpu사용시간에 비례한다. 즉 이 말은 
