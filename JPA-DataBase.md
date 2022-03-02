# JPA

## N+1 문제

```text
JpaRepository에 정의한 인터페이스 메서드를 실행하면 JPA는 메서드 이름을 분석해서 JPQL을 생성하여 실행하게 된다. JPQL은 SQL을 추상화한 객체지향 쿼리 언어로서 특정 SQL에 종속되지 않고 엔티티 객체와 필드 이름을 가지고 쿼리를 한다. 그렇기 때문에 JPQL은 findAll()이란 메소드를 수행하였을 때 해당 엔티티를 조회하는 select * from Owner 쿼리만 실행하게 되는것이다. JPQL 입장에서는 연관관계 데이터를 무시하고 해당 엔티티 기준으로 쿼리를 조회하기 때문이다. 그렇기 때문에 연관된 엔티티 데이터가 필요한 경우, FetchType으로 지정한 시점에 조회를 별도로 호출하게 된다.
```

`Fetch join` 으로 해결해보자.

- INNER JOIN

```java
@Query("SELECT DISTINCT o FROM Owner o JOIN FETCH o.cats")
List<Owner> findAllJoinFetch();
```

장점

- 연관관계의 연관관계가 있을 경우에도 `하나의 쿼리 문으로 표현`

단점

- Fetch Join을 사용하게 되면 데이터 `호출 시점에 모든 연관 관계의 데이터를 가져오기 때문에` FetchType을 Lazy로 해놓는것이 무의미
- 하나의 쿼리문으로 데이터를 가져오다 보니 `페이징 쿼리를 사용할 수 없음`

`EntityGraph` 로 해결해보자.

- OUTER JOIN

```java
@EntityGraph(attributePaths = "cats")
@Query("select o from Owner o")
List<Owner> findAllEntityGraph();
```

- attributePaths에 쿼리 수행시 바로 가져올 필드명을 지정하면 Lazy가 아닌 Eager 조회

`중복 데이터 처리`

- Fetch Join과 EntityGraph 사용 시 JOIN 문이 호출되면서 카테시안 곱이 발생한다. 즉, 중복 데이터가 존재할 수 있다.
  - distinct를 사용하여 중복을 제거
  - 일대다 필드의 타입을 LinkedHashSet으로 선언 (Set은 순서 비보장이므로 LinkedHashSet을 사용하여 순서를 보장)

[N+1 문제](https://incheol-jung.gitbook.io/docs/q-and-a/spring/n+1)

[JPA N+1 문제 및 해결방안](https://jojoldu.tistory.com/165)

## 무한 참조

## JPA N+1 문제에서 fetchJoin, 일반 join 의 경우 몇 개가 출력되는지

## 단방향 양방향 데이터 바인딩의 차이

## 기본 원리

# DataBase

데이터베이스 정규화 과정에 대해 설명해주세요.

해시테이블에 대해 설명해주세요.

데이터베이스 트랜잭션이란 무엇인가요?

쿼리가 들어올 때, 어떻게 해야 효과적으로 저장할 수 있나요?

디비 풀은 왜 쓰나요?

디비 실시간 통신과 디비풀 이용시의 차이가 무엇인가요?

SQL에서 left join에 대해 설명하시오.

RDBMS와 NoSQL의 차이는?

index에 대한 설명과 장/단점으로 무엇이 있나요.

몽고DB의 특성에 대해 설명해주세요.

SQL Injection은 무엇인가요?

ACID에 대해 설명해주세요. (Atomic, Consistency, Isolation, Durability)

1차 정규화, 2차 정규화, 3차 정규화, BCNF에 대해 설명해주세요.