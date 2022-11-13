
# JPA
<br>

-----------------------
### 왜 JPA를 선택했나요? JPA가 MyBatis 대비해서 갖는 장점이 무엇인가요?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

-----------------------
+
</details>

-----------------------

### JPA와 SPRING DATA JPA의 차이점은 무엇인가요?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

-----------------------
+ SPRING DATA JPA는 CRUD를 처리하기 위한 공통 인터페이스를 제공합니다. 
  즉, 구현 클래스 없이 인터페이스만 작성해도 개발을 완료할 수 있게 해줍니다. 
</details>

-----------------------

### @GeneratedValue란 무엇인가요? 이것을 사용하는 이유는 무엇인가요? 

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

-----------------------
+ PK의 값을 위한 생성 전략을 구체화하기 위해서 사용합니다. <br>
  ex) @GeneratedValue(strategy = GenerationType.IDENTITY)
  
</details>

-----------------------

### 생성 전략이란 무엇인가요? 

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

-----------------------
+ 생성 전략이란 JPA Entity의 PK를 생성하기 위한 전략을 의미하며, <br>
  대표적인 것으로 AUTO, IDENTITY, SEQUENCE, TABLE 등이 있습니다. <br>
  AUTO란 영속성 제공자가 특정 DB를 위해 알맞은 전략을 선택해야 한다는 것이며, <br>
  IDENTITY란 영속성 제공자가 데이터베이스 IDENTITY 칼럼을 활용해서 PK를 할당해야 한다는 것이며, <br>
  SEQUENCE란 영속성 제공자가 데이터베이스 SEQUENCE에 따라 PK를 할당해야 한다는 것이며, <br>
  TABLE이란 영속성 제공자가 유일성 보장을 위해 데이터베이스 테이블에 따라 PK를 할당해야 한다는 것입니다. 
  
</details>

-----------------------

### @Column이란 무엇인가요?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

-----------------------
+ 영속성 property 혹은 필드를 위한 매핑된 칼럼을 구체화하기 위해서 사용합니다. 
</details>

-----------------------

### @Enumerated란 무엇인가요?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

-----------------------
+ 영속성 property 혹은 필드가 enumerated type으로 영속화되어야 한다는 것을 의미합니다. 
</details>

-----------------------

