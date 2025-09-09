
### **recursive_mutex**  **가 데드락 안 걸리는 이유**

  

recursive_mutex는 내부적으로 **“누가 이 락을 소유했는지” + “몇 번 lock 했는지” 카운터**를 관리해요.

1. 처음 lock() → 소유자(owner thread ID) 기록, lock count = 1
    
2. 같은 스레드가 또 lock() → **owner가 같으면 허용**, lock count++
    
3. 다른 스레드가 lock() → block (owner가 다름)
    
4. unlock() → lock count–
    
5. lock count가 0이 되면 owner 해제 → 이제 다른 스레드가 들어올 수 있음