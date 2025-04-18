##### FCFS (first-come first-served) 
들어온 순서대로 실행하는 스케줄링

##### SJF (shortest-Job-First)
가장 짧은 프로세스를 제일 먼저 스케줄
minimum average wating time을 보장 starvation(기아 현상)발생가능 

#### Round Robin(RR)
각 프로세스는 **동일크기의 cpu 할당시간**을 가진다.
할당시간이 끝나면 **인터럽트 발생** 프로세스는 cpu를 빼앗기고 cpu큐의 제일 뒤에 줄을 섬.
##### 고려해야 될 점

- 첫번째 프로세스의 waiting time은 0.
- 마지막 프로세스는 waiting time은 없다.
- cpu 할당시간은 운영체제가 정한다.