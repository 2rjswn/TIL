# cookie
웹 서버가 생성하여 웹 브라우저로 전송하는 작은 데이터이다.      
웹 브라우저는 수신한 쿠키를 정해진 기간 동안 또는 웹 사이트에서의 사용자 세션 기간 동안 저장한다.      
## 특징
- 4kb 의 용량
- 만료 기간 설정 가능하다.
- http 요청시 따로 설정하지 않아도 자동으로 전달한다.
- XSS,XSRF 공격에 취약하다.

## 쿠키의 유형

### 세션 쿠키
세션 쿠키는 웹 브라우저를 닫을 때까지 유지되는 일시적인 쿠키로, 사용자의 세션 정보를 유지하고 관리하는 데 사용된다.     
브라우저가 종료되면 자동으로 삭제된다.        

### 영구 쿠키
브라우저를 닫아도 삭제되지 않고, 설정된 만료 날짜까지 유지되는 쿠키로,      
로그인 상태 유지나 사용자 설정을 저장하는 데 사용된다.

### 인증 쿠키
사용자의 로그인 상태를 유지하기 위해 생성되는 쿠키로,       
웹사이트에서 사용자를 인증하고 세션을 유지하는 데 사용된다.

### 추적 쿠키
사용자의 웹 활동을 추적하기 위해 사용되는 쿠키로,
주로 맞춤형 광고 제공이나 웹사이트 분석을 위해 사용된다.

### 좀비 쿠키
사용자가 삭제해도 자동으로 다시 생성되는 쿠키로, 추적이나 인증을 지속하기 위해 사용되며,        
프라이버시 문제를 일으킬 수 있다.