# TCP
연결지향적 프로토콜이다. (데이터를 전송하는 측과 데이터를 받는 측에서 전용의 데이터 전송 선로를 만든다는 의미)         
TCP는 가상의 회선을 만들어 신뢰성을 보장하도록 하는 프로토콜로 따로 신뢰성을 보장하기 위한 절차가 없는 UDP에 비해 속도가 느리다.

# UDP
데이터를 데이터그램(패킷 교환 네트워크와 관련된 기본 전송 단위)로 전송하는 프로토콜이다.        
UDP도 신뢰성을 보장하지 않는 것 뿐이지 개발자가 직접 신뢰성을 보장하게 할 수 있다.        

TCP는 중요한 문서, 파일 전송과 같이 신뢰성이 중요한 서비스에 사용되고 UDP는 스트리밍, RTP와 같이 연속성이 더 중요한 서비스에 사용된다.

---

# TCP 3, 4way handshake
위에서 TCP는 가상회선을 만든다 했는데 3-Way Handshake 는 TCP의 접속,4-Way Handshake는 TCP의 접속 해제 과정이다.      
SYN : 연결설정, ACK : 응답확인, FIN : 연결해제        
## 3-Way Handshake
3way handshake는 양쪽 모두 데이터를 전송할 준비가 되어있다는 것을 보장하고,        
실제로 데이터 전달이 시작하기 전에 다른 한쪽이 준비되었다는 것을 알 수 있도록 해준다.
1. Client가 Server에게 접속을 요청하는 SYN플래그를 보낸다.
2. Server는 Listen상태에서 SYN이 들어온 것을 확인하고 SYN_RECV상태로 바뀌어 SYN + ACK플래그를 Client에게 전송한다.        
그 후 Server는 다시 ACK 플래그를 받기 위해 대기상태로 변경된다.
3. SYN + ACK 상태를 확인한 Client는 서버에게 ACK를 보내고 연결 성립이 된다.        
![스크린샷 2024-08-10 220856](https://github.com/user-attachments/assets/014b0522-14a1-4c64-aa3f-62de69b0814d)

## 4-Way Handshake
4way handshake는 세션을 종료하기 위해 수행되는 절차를 말한다.
1. Client가 연결을 종료하겠다는 FIN플래그를 전송한다.
2. FIN 플래그를 받은 Server는 확인메세지인 ACK를 Client에게 보내준다.
3. Close준비가 다 된 후 Server는 Client에게 FIN 플래그를 전송한다.
4. Client는 해지 준비가 되었다는 정상응답인 ACK를 Server에게 보내준다.          
![image](https://github.com/user-attachments/assets/52a756ae-ca7e-459a-9884-7410cba25caa)

