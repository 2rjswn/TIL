# 전략 패턴
객체지향 디자인 패턴 중 하나로 알고리즘 군을 정의하고 해당 알고리즘들을 캡슐화하여 교환이 가능하도록 만드는 패턴이다.          
상속이 많아져서 중복이 많을 때 고려하면 좋다.          
# 주요 구성 요소
전략 인터페이스 : 알고리즘을 정의하는 인터페이스 다양한 알고리즘이 이 인터페이스를 정의한다.             
구체적인 전략 클래스 : 인터페이스를 구현하는 클래스들으로 각각의 구체적인 알고리즘을 정의한다.              
컨텍스트 클래스 : 클라이언트로부터 특정 전략을 전달받아 그 전략을 사용하는 클래스이다.               
# 장점
유연성: 알고리즘을 런타임에 변경할 수 있어 코드의 유연성이 증가한다.           
유지보수성: 각 알고리즘이 별도의 클래스에 캡슐화되어 있어 수정이나 확장이 용이하다.              
재사용성: 다양한 컨텍스트에서 동일한 전략을 재사용할 수 있다.                
# 단점
객체 수 증가, 인터페이스 관리 추가, 클라이언트 코드 복잡성 증가
