# JPA 성능 최적화  
<br>

### JPA N+1 문제란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 자바 ORM 표준 JPA 프로그래밍] 
  
+ JPA로 애플리케이션을 개발할 때, 성능상 가장 주의해야 하는 것이 N+1문제입니다. <br> 
  
  ```
  @Entity
  public class Member{
  
    @Id @GeneratedValue
    private Long id;
  
    @OneToMany(mappedBy = "member", fetch = FetchType.EAGER)
    private List<Order> orders = new ArrayList<Order>(); 
  
  }
  ```
  
  ```
  @Entity
  @Table(name = "ORDERS")
  public class Order{
  
   @Id @GeneratedValue
   private Long id;
  
   @ManyToOne
   private Member member;
 ```
  
 회원과 주문 정보는 1:N, N:1 양방향 연관관계입니다. <br> 
 그리고 회원이 참조하는 주문정보인 Member.orders를 즉시 로딩으로 설정했습니다. <br>   
</details>

-----------------------
  
 ### 즉시 로딩과 N+1문제는 어떻게 연관되는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 자바 ORM 표준 JPA 프로그래밍] 
 
+ 특정 회원 하나를 em.find() 메소드로 조회하면, 즉시 로딩으로 설정한 주문정보도 함께 조회합니다. <br>
  ```
   em.find(Member.class, id); 
  ```
  실행된 SQL은 다음과 같습니다. 
  ```
   SELECT M.*, O.*
   FROM
     MEMBER M 
   OUTER JOIN ORDERS O ON M.ID = O.MEMBER_ID
  ```
  여기서 함께 조회하는 방법이 중요한데, SQL을 두 번 실행하는 것이 아니라 조인을 사용해서 한 번의 SQL로 회원과 주문정보를 함께 조회합니다. <br> 
  여기까지만 보면 즉시 로딩이 상당히 좋아보입니다. <br> 
  문제는 JPQL을 사용할 때 발생합니다. <br> 
  다음 코드를 봅시다. <br> 
  
  ```
  List<Member> members = em.createQuery("select m from Member m", Member.class).getResultList(); 
  ```
  
  JPQL을 실행하면 JPA는 이것을 분석해서 SQL을 생성합니다. <br> 
  이 때는, 즉시 로딩과 지연 로딩에 대해서 전혀 신경 쓰지 않고, JPQL만 사용해서 SQL을 생성합니다. <br> 
  따라서 다음과 같은 SQL이 실행됩니다. <br> 
  ```
    SELECT * FROM MEMBER;
  ```
  SQL의 실행 결과로 먼저 회원 엔티티를 애플리케이션에 로딩합니다. <br> 
  그런데 회원 엔티티와 연관된 주문 컬렉션이 즉시 로딩으로 설정되어 있으므로, <br> 
  JPA는 주문 컬렉션을 즉시 로딩하려고 다음 SQL을 추가로 실행합니다. <br> 
  ```
    SELECT * FROM ORDERS WHERE MEMBER_ID=?
  ```
  조회된 회원이 하나면 이렇게 총 2번의 SQL을 실행하지만, 조회된 회원이 5명이라면 어떻게 될까? <br> 
  
  ```
   SELECT * FROM MEMBER;
   SELECT * FROM ORDERS WHERE MEMBER_ID = 1; // 회원과 연관된 주문
   SELECT * FROM ORDERS WHERE MEMBER_ID = 2; // 회원과 연관된 주문
   SELECT * FROM ORDERS WHERE MEMBER_ID = 3; // 회원과 연관된 주문
   SELECT * FROM ORDERS WHERE MEMBER_ID = 4; // 회원과 연관된 주문
   SELECT * FROM ORDERS WHERE MEMBER_ID = 5; // 회원과 연관된 주문
  ```
  먼저 회원 조회 SQL로 5명의 회원 엔티티를 조회했습니다. <br> 
  그리고 조회한 각각의 회원 엔티티와 연관된 주문 컬렉션을 즉시 조회하려고 <br>
  총 5번의 SQL을 추가로 실행했습니다. <br> 
  이처럼 처음 실행한 SQL의 결과 수만큼 추가로 SQL을 실행하는 것을 N+1문제라 합니다. <br> 
  즉시 로딩은 JPQL을 실행할 때 N+1문제가 발생할 수 있습니다. 
  
</details>

----------------------- 
