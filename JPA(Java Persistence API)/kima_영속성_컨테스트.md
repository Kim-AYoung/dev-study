## 영속성 컨테스트
쿼리를 사용하지 않고도, 트랜잭션이 끝나는 시점에 영속성 컨테스트 안에 변화가 있는 모든 엔티티 객체를 DB에 자동으로 반영해준다.
* Entity Manager는 영속성 컨텍스트 내부에서 엔티티 CRUD 같이 엔티티와 관련된 모든 일을 처리한다.
  * JPA의 Entity Manager가 활성된 상태이어야한다.
* Spring data jpasms 영속성 컨텍스트를 기본 옵션으로 가지고 있다.

## 장점
1. 1차 캐시 : 엔터티를 캐시에 임시보관하여, DB에서 엔티티를 불러오는 시간을 단축한다.
2. 동일성 보장
3. 트랜잭션을 지원하는 쓰기 지연 : 트랜잭션이 커밋되면, DB에서 자동으로 쿼리문이 실행된다.
4. 변경 감지 (dirty check) : 트랜잭션을 커밋하는 순간, 영속성 컨텍스트에 있는 엔티티의 변경 내용을 DB에 반영한다. (=FLUSH)

## Entity Life Cycle
![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6f7c7d94-2077-4bed-be72-b35a19aed2e6/Untitled.png)
* 비영속(new/transient) : 영속성 컨텍스트와 전혀 관계가 없는 상태
* 영속(managed) : 영속성 컨텍스트에 저장된 상태
  * `detach()` : 영속상태의 엔티티를 영속성 컨텍스트에서 분리
  * `clear()` : 영속상태의 모든 객체를 영속성 컨텍스트에서 분리
  * `close()` : 영속성 컨텍스트 종료
* 준영속(detached) : 영속성 컨텍스트에 저장되었다가 분리된 상태
* 삭제(removed) : 엔티티를 영속성 컨텍스트에서 분리하고, DB에서도 삭제한 상태

  
