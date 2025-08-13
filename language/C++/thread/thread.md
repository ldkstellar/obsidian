주요 메서드 및 특징
- std::thread t(func) 새로운 스레드 생성및 함수 실행
- t.join(): 해당 스레드가 종료될 때까지 기다림(blocking)
- t.detach(): 스레드를 분리하여 백그라운드에서 실행
- t.joinable(): join 또는 detach 가능한 상태인지 확인

