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

## JPA, Hibernate, Spring Data JPA

**JPA**

- Java Persistence API의 약자, 단순한 기술 명세서
- 자바 어플리케이션에서 관계형 데이터베이스를 사용하는 방식을 정의한 `인터페이스`, 어떻게 사용해야 하는지를 정의하는 한 방법

**Hibernate**

- JPA라는 명세의 구현체 (JPA 인터페이스를 직접 구현한 라이브러리)
- Hibernate 뿐만 아니라 DataNucleus, EclipseLink 등 다른 JPA 구현체도 존재

**Spring Data JPA**

- JPA를 쓰기 편하게 만들어놓은 모듈
- Repository가 바로 Spring Data JPA의 핵심
- 개발자가 JPA를 더 쉽고 편하게 사용할 수 있도록 도와준다

<https://suhwan.dev/2019/02/24/jpa-vs-hibernate-vs-spring-data-jpa/>


JPA에서 DB transaction이 어떻게 작동하는지