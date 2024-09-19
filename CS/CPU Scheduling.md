# CPU Scheduling
CPU가 하나의 프로세스 작업이 끝나면 다음 프로세스 작업을 수행해야 한다.                  
이때 다음 프로세스가 어느 프로세스인지를 선택하는 알고리즘을 CPU Scheduling 알고리즘이라고 한다.                   
CPU 스케줄링에는 여러가지 방법이 존재한다.
## 1 Preemptive(선점), Non-preemptive(비선점)
Preemptive는 프로세스가 CPU를 점유하고 있는 동안 인터럽트 없이 작업을 끝내지도 않고 다른 프로세스가 해당 CPU를 강제로 점유 할 수 있다.               
Non-preemptive프로세스가 한 번 CPU를 점유했다면 대기로 변경되는 경우 또는 프로세스가 종료될 때까지 다른 프로세스가 CPU를 점유하지 못하는 것이다.
## Scheduling criteria
Scheduling criteria(척도)는 스케줄링의 효율을 분석하는 기준들이다.           
- CPU Utilization(이용률, %): CPU가 수행되는 비율
- Throughput(처리율, jobs/sec): 단위시간당 처리하는 작업의 수(처리량)
- Turnaround time(반환시간): 프로세스의 처음 시작 시간부터 모든 작업을 끝내고 종료하는데 걸린 시간이다. 반환시간은 짧을 수록 좋다.
- Waiting time(대기시간): CPU를 점유하기 위해서 ready queue에서 기다린 시간을 말한다.
- Response time(응답시간): 일반적으로 대화형 시스템에서 입력에 대한 반응 시간을 말한다.
## CPU Scheduling Algorithms
1. First-Come, First-Served         
먼저 온 프로세스가 먼저 CPU를 점유하는 방식이다.
2. Shortest-Job-First(SJF)            
가장 짧게 수행되는 프로세스가 가장 먼저 수행되는 것을 말한다.
3. Priority                
우선순위가 높은 프로세스가 먼저 선택되는 스케줄링 알고리즘이다.               
우선순위는 정수값으로 나타내며, 작은 값이 우선순위가 높다.
4. Round-Robin(RR)                 
원 모양으로 모든 프로세스가 돌아가며 스케줄링하는 것을 말한다.                   
시분활 시스템에서 주로 사용한다.                    
일정 시간을 정하고 프로세스들은 딱 그 시간동안 수행하고 대기한다.
5. Multilevel Queue                        
여러 성격에 따라 프로세스 그룹을 나눌 수 있는데 이를 하나의 큐에 사용하는 것은 비효율적이여서 각 그룹에 따라 큐를 두어 여러 개의 큐를 사용하는 방식이다.
6. Multilevel Feedback Queue             
모든 프로세스는 가장 위의 큐에서 CPU의 점유를 대기하고 너무 오래걸리면 아래의 프로세스로 옮긴다.
starvation 상태가 발생하면 이를 우선순위가 높은 위의 큐로 옮길 수도 있다.
