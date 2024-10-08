# database
데이터베이스란 전자적으로 저장되고 체계적인 데이터 모음이다.        
데이터배이스를 사용하는 이유는 원래 파일로 데이터를 저장했지만 중복, 검색 문제를 해결하기 위해 데이터베이스를 사용한다.      
## DBMS
데이터베이스 관리 시스템으로 여러 사용자가 데이터베이스로 접근하고 사용할 수 있도록 해주는 소프트웨어 이다.     
## Key
검색, 정렬 시 튜플을 구분하는 기준이 되는 속성이다. (튜플이란 자료구조인데 여러개의 데이터를 담아두는데 사용된다. 배열과 다른점은 추가, 삭제, 수정이 안됀다.)
key에는 5가지 종류가 있는데 기본키, 대채키, 후보키, 슈퍼키, 외래키가 있다.
1. 기본키 : null값을 가질 수 없고 중복일 수 없다.
2. 대채키 : 말 그대로 보조키 이다.
3. 후보키 : 기본키로 선택될 수 있는 후보들이고 유일성과 최소성이 필요하다.
4. 슈퍼키 : 유일성은 말족할 수 있지만 최소성은 만족하지 않아도 된다.
5. 외래키 : 다른 테이블의 키를 참조하는 테이블간을 연결함
## Join
1. inner join
- 기준 테이블과 중복된 값을 가진다.
2. left outer join
- join 테이블이 기준 테이블의 중복된 값만 보여준다 만약 없다면 NULL로 표기한다.
3. right outer join
- 2번의 반대이다.
4. full outer join
- 2번과 3번이 합쳐진 값들이다.
5. cross join
- 각테이블을 곱한 값들이다.
6. self join
- 자신의 테이블을 각각 곱한 값들이다.
## Transaction
데이터베이스의 상태를 변환시키기 위해 수행하는 작업 단위이다. (sql을 사용하여 상태를 변환시킨다.)
### Transaction 특징
1. 원자성 : 트랜잭션이 DB에 전부 반영되거나 반영되지 않아야 한다.
2. 일관성 : Transaction 작업 처리는 항상 일관적이여야 한다.
3. 독립성 : 둘 이상의 Transaction이 동시에 병행 실행되고 있을땐 어떤 다른 Transaction도 끼어들 수 없다.
4. 지속성 : Transaction이 성공적으로 실행되면 그 결과는 영구적으로 반영되어랴 한다.
# Index
추가적인 공간을 활용해 테이블의 검색속도를 향상시키는 자료구조이다.       
데이터를 조회하는 SELECT 말고도 데이터를 지우거나 업데이트 할때도 조회를 한 후 가능하기 때문에 UPDATE와 DELETE도 성능이 향상된다.      
DBMS에서는 Index를 항상 최신화를 해줘야해서 INSERT, UPDATE, DELETE 가 수행된다면 연산을 추가적으로 해주어야한다.         
## 장점
- 조회하는 속도가 빨라져 성능이 향상된다.
## 단점
- DB의 10% 에 해당하는 저장공간이 필요하다.
- 인덱스를 잘 관리하지 못하면 오히려 성능이 저하되고 관리하기 위해서도 추가작업이 필요하다.
- CREATE, DELETE, UPDATE 가 너무 빈번히 사용되면 인덱스의 크기가 너무 커져 오히려 성능저하가 된다.
따라서 인덱스를 사용할 때는 CREATE, DELETE, UPDATE가 빈번하지 않고 데이커 중복이 적고 규모가 큰 테이블에서 사용하기 좋다.
# NoSQL
SQL만을 사용하지 않는 데이터베이스 관리 시스템이다.       
특징으로는 형태가 자유롭고 언제든지 데이터를 조정하고 새로운 필드를 추가할 수 있고 트래픽 분산 및 대용량 처리가 가능하다.      
정확한 데이터 구조를 알기 힘들거나 변경 확장이 많이 될 수 있을때 대용량의 데이터를 다룰때 사용하면 좋다.        
# Lock
동시성을 제어할 때 사용한다.      
낙관적 락 과 비관적 락 이 있다.
## Optimistic Lock
동시 업데이트가 거의 없을 경우 사용한다.         
먼저 값을 수정했다고 명시하여 동일한 조건으로 값을 수정할 수 없게 한다.         
DB에서 제공하는 기능이 아닌 Application 에서 해주는 것이다.         
## Pessimistic Lock
동시 업데이트가 빈번한 경우 사용한다.         
읽기 잠금을 하면 데이터를 읽는 동안 해당 데이터에 대한 쓰기 작업을 막고 쓰기 잠금을 하면 해당 데이터에 대해 읽기 및 쓰기 작업을 할 수 없도록 한다.         
