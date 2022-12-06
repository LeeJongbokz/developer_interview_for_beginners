# Java 일반
<br>


### Java interface와 abstract 클래스의 차이점은?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 이펙티브 자바]    
+ 둘의 가장 큰 차이는 추상 클래스가 정의한 타입을 구현하는 클래스는 <br>
  반드시 추상 클래스의 하위 클래스가 되어야 한다는 점이다. <br> 
  
  자바는 단일 상속만 지원하니, 추상 클래스 방식은 새로운 타입을 정의하는데 <br>
  커다란 제약을 안게 되는 셈입니다. <br>
  반면, 인터페이스가 선언한 메서드를 모두 정의하고, 그 일반 규약을 잘 지킨 클래스라면 <br>
  다른 어떤 클래스를 상속했든 같은 타입으로 취급됩니다. <br> 
    
</details>



### Java 11 버전의 특징은?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: https://learn.microsoft.com/ko-kr/java/openjdk/reasons-to-move-to-java-11]    
+ 1) Java11의 기본 가비지 컬렉터는 G1GC입니다. 
     Java8까지는 Parellel GC가 기본 GC였습니다. 
  2) Java 11에는 JVM의 모든 구성 요소에 대한 일반적인 로깅 시스템이 있습니다
     이 통합 로깅 시스템을 통해 사용자는 무슨 구성 요소를 어느 수준까지 로깅할지 정의할 수 있습니다. 
     이 세분화된 로깅은 JVM 충돌에 대한 근본 원인 분석을 수행하고, 
     프로덕션 환경에서 성능 문제를 진단하는 데 유용합니다. 
  
   
</details>


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

### 절차지향 프로그래밍 vs 객체지향 프로그래밍?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: https://www.geeksforgeeks.org/differences-between-procedural-and-object-oriented-programming/]    
   
+ 절차지향 프로그래밍은 구조적 프로그래밍에서 기인한 것인데, 이것은 procedure를 call하는 것에 기반합니다. <br> 
  Procedure는 루틴, 서브루틴, 혹은 함수라고도 불리는데, 이것은 수행되어야 할 일련의 컴퓨터적인 단계를 포함하고 있습니다. <br> 
  프로그램의 실행 과정에서 자기 자신을 호출하는 것을 포함하여, 어떤 프로시저도 어떤 시점에서 실행될 수 있습니다. <br>
   
  객체지향 프로그래밍은 객체에 기반한 프로그래밍 모델로서, <br>
  객체는 속성과 메소드를 지니고 있습니다. <br> 
  객체지향 프로그래밍에서 컴퓨터 프로그램은 실세계와 상호작용하는 객체를 활용하여 디자인됩니다. <br> 
  객체지향 프로그래밍은 다양하지만 가장 인기 있는 것은 클래스에 기반한 것이고, <br> 
  그것은 객체는 클래스의 인스턴스이고, 클래스가 객체의 타입을 결정한다는 것을 의미합니다. 
</details>

-----------------------

### 제네릭의 장점과 단점은?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 이펙티브 자바 p.153]    
   
+ 제네릭은 자바 5부터 사용할 수 있습니다. <br> 
  제네릭을 지원하기 전에는 컬렉션에서 객체를 꺼낼대마다 형변환을 해야 했습니다. <br>
  그래서 누군가 실수로 엉뚱한 타입의 객체를 넣어두면 런타임에 형변환 오류가 나곤 했습니다. <br> 
  
  반면, 제네릭을 사용하면 컬렉션이 담을 수 있는 타입을 컴파일러에 알려주게 됩니다. <br> 
  그래서 컴파일러는 알아서 형변환 코드를 추가할 수 있게 되고, <br>
  엉뚱한  타입의 객체를 넣으려는 시도를 컴파일 과정에서 차단하여, <br>
  더 안전하고 명확한 프로그램을 만들어 줍니다. <br> 
   
  꼭 컬렉션이 아니더라도, 이러한 이점을 누릴 수 있으나, 코드가 복잡해진다는 단점이 따라옵니다. <br>  
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
[참고: 이펙티브 자바] 
+ 열거 타입은 일정 개수의 상수 값을 정의 한 다음, 그 외의 값은 허용하지 않는 타입입니다. <br> 
  사계절, 태양계의 행성, 카드게임의 카드 종류 등이 좋은 예입니다. <br> 
  다음은 열거 타입의 가장 단순한 형태입니다. <br> 
   
  public enum APPLE { FUJI, PIPPIN, GRANNY_SMITH} <br> 
  public enum Orange { NAVEL, TEMPLE, BLOOD} <br> 
   
  겉보기에는 C, C++, C# 같은 다른 언어의 열거 타입과 비슷하지만, <br> 
  보이는 것이 다가 아닙니다. <br> 
  자바의 열거 타입은 완전항 형태의 클래스라서, 다른 언어의 열거 타입보다 훨씬 강력합니다. <br> 
  
  자바 열거 타입을 뒷받침하는 아이디어는 단순합니다. <br> 
  열거 타입 자체는 클래스이며, 상수 하나당 자신의 인스턴스를 하나씩 만들어 <br> 
  public static final 필드로 공개합니다. <br> 
   
  열거 타입은 밖에서 접근할 수 있는 생성자를 제공하지 않으므로, 사실상 final입니다. <br> 
  따라서 클라이언트가 인스턴스를 직접 생성하거나 확장할 수 없으니, <br>
  열거 타입 선언으로 만들어진 인스턴스들은 딱 하나씩만 존재합니다. <br> 
   
  다시 말해 열거 타입은 인스턴스 통제됩니다. <br>
  싱글턴은 원소가 하나뿐인 열거 타입이라 할 수 있고, <br>
  거꾸로 열거 타입은 싱글턴을 일반화한 형태라고 볼 수 있습니다. <br>
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

### 리플렉션의 시작은 무엇인가? 그리고 그것에 접근하는 방법은 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Class<T>입니다. <br> 
  모든 클래스를 로딩 한 다음 Class<T>의 인스턴스가 생깁니다. <br> 
 "타입.class"로 접근할 수 있습니다. <br>
  모든 인스턴스는 getClass() 메소드를 가지고 있습니다. <br>
  "인스턴스.getClass()"로 접근할 수 있습니다. 
</details>

----------------------- 
   
  
### Class<T>를 통해 할 수 있는 것은 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 1) 필드(목록) 가져오기 <br>
  2) 메소드(목록) 가져오기 <br>
  3) 상위 클래스 가져오기 <br> 
  4) 인터페이스 (목록) 가져오기 <br>
  5) 애노테이션 가져오기
  6) 생성자 가져오기
   
</details>

----------------------- 


### 중요 어노테이션인 @Retention, @Inherit, @Target은 각각 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ @Retention: 해당 애노테이션을 언제까지 유지할 것인가? 
  @Inherit: 해당 애노테이션을 하위 클래스까지 전달할 것인가?
  @Target: 어디에 사용할 수 있는가? 
   
</details>

----------------------- 

### 리플렉션의 getAnnotations()와 getDeclaredAnnotations()의 차이점은 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ getAnnotations()는 상속받은(@Inherit) 애노테이션까지 조회합니다. 
  getDeclaredAnnotations()는 자기 자신에만 붙어 있는 어노테이션을 조회합니다. 
   
</details>

----------------------- 


### 리플렉션 API에서 생성자로 인스턴스를 어떻게 만드는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Constructor.newInstance(params)로 만든다. 
   
</details>

----------------------- 
 

### 리플렉션 API에서 필드 값을 어떻게 접근하고 설정하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Field.get(object), Field.set(object, value)를 통해 접근하고 설정한다. 
   
</details>

----------------------- 
   
### 리플렉션 API에서 메소드는 어떻게 실행하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Object Method.invoke(object, params)를 통해 실행한다. 
   
</details>

----------------------- 


### 리플렉션 사용시 주의할 점은 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 1) 지나친 사용은 성능 이슈를 야기할 수 있으므로, 반드시 필요한 경우에만 사용한다. <br>
  2) 컴파일 타임에 확인되지 않고, 런타임 시에만 발생하는 문제를 만들 가능성이 있다. <br> 
  3) 접근 지시자를 무시할 수 있다. 
   
</details>

----------------------- 

   
### 리플렉션의 사용 예시에는 무엇이 있는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 스프링의 의존성 주입, mvc 뷰에서 넘어온 데이터를 객체에 바인딩할 때 <br>
  하이버네이트의 @Entity 클래스에 Setter가 없다면 리플렉션을 사용 <br>
  JUnit은 ReflectionUtils 
   
</details>

----------------------- 
   
   
### 리플렉션의 사용 예시에는 무엇이 있는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 스프링의 의존성 주입, mvc 뷰에서 넘어온 데이터를 객체에 바인딩할 때 <br>
  하이버네이트의 @Entity 클래스에 Setter가 없다면 리플렉션을 사용 <br>
  JUnit은 ReflectionUtils 
   
</details>

----------------------- 
   

### 다이나믹 프록시는 무엇의 일부인가? 프록시가 사용되는 대표적인 예가 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 리플렉션의 일부입니다. <br> 
  스프링 데이터 JPA입니다. <br>  
   
</details>

-----------------------    
   
   
### 스프링 데이터 JPA에서는 무엇을 쓰는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 스프링 AOP를 활용한다. <br> 
   
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
