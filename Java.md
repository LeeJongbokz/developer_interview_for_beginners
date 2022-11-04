# Java
<br>




### 객체지향 프로그래밍 vs 절차지향 프로그래밍?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>



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
### equals 메소드란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>

-----------------------


### hashCode 메소드란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>


-----------------------
### equals를 재정의할 때, 반드시 hashCode도 재정의해야 하는데 이유는 무엇인가요?

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

### 람다 표현식이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 람다 표현식은 메서드를 하나의 식으로 표현한 것을 의미합니다. 
  람다 표현식은 함수형 프로그래밍의 특징을 갖고 있습니다.  
  람다 표현식의 장점은 불필요한 코드를 줄여주고, 가독성을 높여준다는 점입니다. 
</details>


-----------------------

### 함수형 프로그래밍이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>

-----------------------

### 메소드 레퍼런스란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>

-----------------------
### Stream이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 연속된 데이터를 처리하는 순차적이고 병렬적인 집합 Operation의 모음입니다. 
  Stream은 Functional하고, 소스를 변경하지 않는다는 특징이 있습니다. 
</details>


-----------------------

### Stream pipe line이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
   
+ 다수의 중개 오퍼레이션과 하나의 종단 오퍼레이션으로 구성된 스트림의 구성을 의미합니다.  <br>
</details>

-----------------------

### parellelStream이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
   
+ 병렬적으로 처리를 해주는 Stream을 의미합니다. <br>
  단, parellelStream을 쓴다고 항상 빨라지는 것이 아님을 주의해야 합니다.  <br>
  스레드를 생성하고, context switching하는 비용을 고려해야 하기 때문입니다.  <br>
  데이터가 방대한 경우는 병렬 처리가 유리할 수 있습니다.  <br>
  각 케이스에 대해 성능 측정을 해야 합니다.  <br>
</details>


-----------------------

### Fork join pool이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
   
+ 
</details>


-----------------------
### Stream의 map과 flatMap의 차이점은?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
   
+
</details>


-----------------------
### Stream의 forEach와 map의 차이점은?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
   
+
</details>


-----------------------

### Java에서 Null 처리는 어떻게 하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
   
+
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
