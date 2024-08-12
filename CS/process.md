# process
- process 실행중에 있는 프로그램(Program)을 의미한다.       
- 스케줄링의 대상이 되는 작업(task)과 같은 의미로 쓰인다.
- 프로세스 내부에는 최소 하나의 스레드(thread)를 가지고있는데, 실제로는 스레드(thread)단위로 스케줄링을 한다.
- 하드디스크에 있는 프로그램을 실행하면, 실행을 위해서 메모리 할당이 이루어지고,
할당된 메모리 공간으로 바이너리 코드가 올라가게 된다. 이 순간부터 프로세스라 불린다.
# process의 구조
프로세스를 실행시키기 위해서는 메모리 할당을 해야하는데, 이때 프로세스마다 고유한 가상 메모리 공간이 주어진다.
![image](https://github.com/user-attachments/assets/ee0eebd0-930c-4633-bda7-35aa87e982bb)         
1. Text      
내 코드가 저장되는 공간으로 코드가 컴파일 되어 0과 1의 기계어로 저장된다.
2. Data       
내 코드의 변수(전역 변수, 정적 변수, 상수)를 저장하는데 초기화된 변수와 그렇지 않은 변수로 나위어서 저장된다.
프로그램 시작 시 초기되며, 프로세스 종료 때까지 유지된다.
3. Stack        
내 코드의 함수에서 변수(지역 변수, 매개 변수), 리턴 주소를 저장하는데 함수가 호출되면 stack공간이 생성되고 함수가 종료되면 사라진다.
4. Heap        
내 코드의 동적으로 생성되는 데이터 구조나 객체들을 저장한다.         
데이터가 추가됨에 따라 유동적으로 공간을 늘릴 수 있는게 힙 영역이다.
# process의 상태
컴퓨터는 프로세스를 처리할 때 5가지의 프로세스의 상태 생명주기에 따라 프로그램을 처리한다.
1. new       
생성만 되고 실행되기 위한 자원을 할당받지 못한 상태이다.
2. Ready
실행을 기다리는 상태 아직 cpu를 할당받지 못한 상태이다.
CPU를 할당받기 위해 스케줄링 대기열(Queue)에 들어가게 된다.
3. Running
코드를 실행하는 상태이다.
4. Blocked
작업 시간이 초과되거나 자원 사용을 위해 대기해야하는 상태이다.
CPU를 사용하지 않고 대기열(Queue)에 들어가게 된다.
5. exit
종료된 상태이다.       
