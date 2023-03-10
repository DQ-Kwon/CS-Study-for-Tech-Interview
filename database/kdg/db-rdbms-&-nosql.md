# CS Study - DB

빠른 이동
|<- 이전 | 현재 | 다음 ->|
|:---:|:---:|:---:|
|[트랜잭션과 무결성](./db-transaction-&-integrity.md)|DB의 종류|[인덱스](./db-index.md)|

## 4. 데이터베이스의 종류

- ### 관계형 데이터베이스

  객체를 관계형으로 구성하는 데이터베이스를 RDB라고 함  
  RDBMS(Relantionship DBMS)를 사용(기존의 DBMS)  
  RDB를 관리하는 시스템이며 RDB는 관계형 데이터 모델을 기초로 두고 모든 데이터를 2차원 테이블 형태로 표현하는 데이터베이스  
  <br/>

- ### NoSQL 데이터베이스

  빅데이터의 등장으로 인해 데이터와 트래픽이 기하급수적으로 증가함에 따라 RDBMS에 단점인 성능을 향상시키기 위해서는 장비가 좋아야 하는 Scale-Up의 특징이 비용을 기하급수적으로 증가시키기 때문에 데이터 일관성은 포기하되 비용을 고려하여 여러 대의 데이터에 분산하여 저장하는 Scale-Out을 목표로 등장

  NoSQL(Not Only SQL)은 RDB가 아닌 다른 형태의 데이터 저장 기술을 의미  
   RDBMS와는 달리 테이블 간 관계를 정의하지 않음  
   테이블 간의 관계를 정의하지 않아 일반적으로 테이블 간 Join도 불가능  
   <br/>

  NoSQL 분류

  1. Key-Value Database

     - 데이터를 Key와 Value의 쌍으로 저장
     - 값은 어떠한 형태의 데이터라도 담을 수 있음(이미지, 비디오 가능)
     - 간단한 API를 제공하는 만큼 질의의 속도가 빠른 편
     - Redis, Riak, Amazon Dynamo DB 등  
       <br/>

  2. Document Database

     - 데이터를 Key와Document의 형태로 저장
     - Key-Value 모델과 다른 점은 Value가 계층적인 형태인 도큐먼트로 저장
     - 객체지향에서의 객체와 유사, 하나의 객체를 여러 개의 테이블에 나눠 저장할 필요가 없어짐
     - 사용이 번거롭고 쿼리가 SQL과는 다름 도큐먼트 모델에서는 질의의 결과가 JSON이나 xml 형태로 출력됨
     - MongoDB, CouthDB 등  
       <br/>

  3. Wide Column Database

     - Column-family Model 기반의 Database이며 키에서 필드를 결정
     - 키는 Row(키 값)와 Column-family, Column-name을 가진 형태로 계층적인 구조
     - 연관 데이터들은 같은 Column-family 안에 속하고, 각 Column-name을 가짐
     - 질의는 Row, Column-family, Column-name을 통해 수행됨
     - HBase, Hypertable 등  
       <br/>

  4. Graph Database

     - 데이터를 Node와 Edge, Property와 함께 그래프 구조를 사용하여 데이터를 저장
     - 개체와 관계를 그래프 형태로 표현한 것이므로 일종의 관계형 모델이라고 할 수 있음
     - 데이터 간의 관계가 탐색의 키일 경우에 적합. 연관된 데이터를 추천해주는 질의 사용
     - Neo4J 등  
       <br/>

- ### RDBMS와 NoSQL 비교

  비교표
  | 비교 | RDBMS | NoSQL |
  | --- | --- | --- |
  | 장점 | - 명확한 RDB 데이터 구조를 보장 <br/> - 관계는 각 데이터를 중복 없이 한 번만 저장할 수 있음 | - 스키마가 없기 때문에 유연하며 자유로운 데이터 구조를 가짐 <br/> - 언제든 저장된 데이터를 조정하고 새로운 필드를 추가할 수 있음 <br/> - 데이터 분산이 용이하며 성능 향상을 위한 Saclue-up 뿐만이 아닌 Scale-out 또한 가능 |
  | 단점 | - 테이블 간 관계를 맺고 있어 시스템이 커질 경우 JOIN문이 많은 복잡한 쿼리를 작성 <br/> - 성능 향상을 위해 Scale-up만을 지원함 (시스템이 커지면 비용이 비쌈) <br/> - 스키마를 사용한 설계 구조로 인해 데이터가 유연하지 못함 | - 데이터 중복이 발생할 수 있으며 중복된 데이터가 변경 될 경우 수정을 모든 컬렉션에서 수행을 해야 함 <br/> - 스키마가 존재하지 않기에 명확한 데이터 구조를 보장하지 않고 데이터 구조 설계가 어려움 |

  <br/>
