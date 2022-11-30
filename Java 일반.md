# Java 일반
<br>


-----------------------

### equals(), hashCode()는 어떻게 오버라이딩 해야 하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ Object에서 final이 아닌 메서드(equals, hashCode, toString, clone, finalize)는 모두 재정의(overriding)를 염두에 두고 설계된 것이라<br>
  재정의 시 지켜야 하는 일반 규약이 명확히 정의되어 있습니다. <br>
  equals는 일반 규약을 지켜 재정의해야 합니다. <br>
  Object 명세에 적힌 규약으로서, 반사성, 대칭성, 추이성, 일관성, null-아님을 만족시켜야 합니다. <br> 
  equals를 재정의한 클래스 모두에서 hashCode도 재정의해야 합니다. <br>
  그렇지 않으면 hashCode 일반 규약을 어기게 되어, 해당 클래스의 인스턴스를 HashMap이나 HashSet 같은 컬렉션의 원소로 사용할 때 <br>
  문제를 일으킵니다. <br>
  논리적으로 같은 객체는 같은 해시코드를 반환해야 합니다. <br> 
  equals는 물리적으로 다른 두 객체를 논리적으로 같다고 할 수 있는데, Object의 기본 hashCode 메서드는 이 둘이 전혀 다르다고 판단하여 <br>
  규약과 달리 (무작위처럼 보이는) 서로 다른 값을 반환합니다.
</details>


-----------------------

### 객체지향 프로그래밍 vs 절차지향 프로그래밍?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>

-----------------------

### try-with-resource란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>

-----------------------
### inner 클래스란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>

-----------------------
### static inner 클래스란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>

-----------------------

### enum이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ enum은 열거 자료형이라고 하며, 고정 개수의 상수들로 값이 구성되는 자료형입니다. 
</details>

-----------------------

### 리플렉션이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 구체적인 클래스 타입을 모르더라도, 해당 클래스의 정보에 접근할 수 있게 해주는 자바 API입니다. <br> 
  java.lang.reflect의 핵심 리플렉션 기능(core reflection facility)을 이용하면
  메모리에 적재된(load) 클래스의 정보를 가져오는 프로그램을 작성할 수 있습니다. 
  
  Class 객체가 주어지면, 해당 객체가 나타내는 클래스의 생성자, 메서드, 필드 등을 나타내는
  Constructor, Method, Field 객체들을 가져올 수 있는데,
  이 객체들을 사용하면 클래스의 멤버 이름이나 필드 자료형, 메서드 시그니처 등의 정보들을 얻어낼 수 있다. 
</details>

-----------------------

### 리플렉션의 시작은 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Class<T>입니다. <br> 
</details>

----------------------- 

### Checked Exception vs Unchecked Exception?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Exception은 크게 Checked Exception과 Unchecked Exception(=Runtime Exception)으로 구분됩니다.<br> 
  Checked Exception은 컴파일 타임에 체크되는 예외로, 메소드나 생성자에 throws 절로 표기되어야 합니다.<br>
  Unchecked Exception은 런타임에 체크되는 예외로, JVM의 동작 과정에서 체크되며, throws 절로 표기될 필요가 없습니다. <br> 
</details>


-----------------------

### 직렬화와 역직렬화란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 직렬화란 객체를 바이트 스트림(byte stream)으로 인코딩(encoding)하는 것을 의미합니다. <br> 
  역직렬화란 바이트 스트림을 객체로 복원하는 것을 의미합니다. <br>
  직렬화는 원격지 VM과 통신하기 위한 표준적 객체 인코딩을 제공합니다.
  직렬화와 역직렬화를 활용하려면 Serializable 인터페이스를 구현해야 합니다. 

</details>


-----------------------

### 바이트 스트림(byte stream)이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+
</details>


-----------------------

### Serializable 인터페이스란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>


-----------------------

### 스레드란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>


-----------------------

### synchronized 키워드란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>


-----------------------

### synchronized 붙으면 JVM 내부에서 어떤 식으로 작동되는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>


-----------------------
