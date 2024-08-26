# TDD(테스트 주도 개발, Test Driven Development) 란?
코드 작성 전에 테스트를 작성하고, 이 테스트에 통과하도록 실제 코드를 작성하는 것이다.           
# TDD의 개발 주기(Red-Green Test)
1. 코드를 작성하기 전에 테스트에 오류가 발생하지 않도록 최소한의 코드를 먼저 작성한다.
2. 이후 기능을 정상적으로 구현했다면 테스트가 통과되도록 테스트 코드를 작성한다.
3. 이후 작성된 테스트를 실행하고 실패를 확인한다. 현재 코드는 최소한의 양만 작성되었기에 당연히 실패한다.
4. 이후 테스트에 통과할 수 있도록 관련 코드를 작성하고, 테스트를 통과시킨다.
# TDD 채용 이유
- 기존 방식의 경우, 매번 애플리케이션을 실행하면서 원하는대로 작동을 하는지 확인하며 소프트웨어를 업데이트 한다.
- 하지만 기능 구현 전에 테스트 코드를 작성하면, 코드를 변경할 시 그와 관련된 테스트가 자동으로 실행된다.
- 따라서 개발을 진행하면서 모든 테스트를 작성해두면 변경 사항이 발생할 때마다 이를 재실행하며 자동으로 테스트를 진행할 수 있다.
- 이는 기존의 수동적인 테스트 방식과는 달리, 매번 서비스를 실행하고 직접 작동하는지 확인할 필요가 없다.