# Java8
<br>



### 람다 표현식이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 람다 표현식은 메서드를 하나의 식으로 표현한 것을 의미합니다. <br> 
  람다 표현식은 함수형 프로그래밍의 특징을 갖고 있습니다. <br>  
  람다 표현식의 장점은 불필요한 코드를 줄여주고, 가독성을 높여준다는 점입니다. <br> 
 
[참고: 이펙티브 자바]    
+ 자바 8에 와서 추상 메서드 하나짜리 인터페이스는 특별한 의미를 인정받아 특별한 대우를 받게 되었습니다. <br> 
  지금은 함수형 인터페이스라 부르는 이 인터페이스들의 인스턴스를 람다식을 사용해 만들 수 있게 된 것입니다. <br> 
  
  람다는 함수나 익명 클래스와 개념은 비슷하지만 코드는 훨씬 간결합니다. <br> 
   
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
[참고: 이펙티브 자바] 
   
+ 람다가 익명 클래스보다 나은 점 중에서 가장 큰 특징은 간결함입니다. <br> 
  그런데 자바에는 함수 객체를 심지어 람다보다도 더 간결하게 만드는 방법이 있으니 <br>
  바로 메서드 참조(method reference)입니다. <br> 
  
  다음 코드는 임의의 키와 Integer의 값의 매핑을 관리하는 프로그램의 일부입니다. <br> 
  이 때, 값이 키의 인스턴스 개수로 해석된다면, <br>
  이 프로그램은 멀티셋(multiset)을 구현한게 됩니다. <br> 
  이 코드는 키가 맵 안에 없다면 키와 숫자 1을 매핑하고, 이미 있다면 기존 매핑 값을 증가시킵니다. <br> 
   
  map.merge(key, 1, (count, incr) -> count + incr); 
   
  이 코드는 자바 8 때 Map에 추가된 merge 메서드를 사용했습니다. <br> 
  merge 메서드는 키, 값, 함수를 인수로 받으며, 주어진 키가 맵 안에 아직 없다면, <br>
  주어진 [키, 값] 쌍을 그대로 저장합니다. <br>
  반대로 키가 이미 있다면, 함수를 현재 값과 주어진 값에 적용한 다음, 그 결과로 현재 값을 덮어씁니다. <br>
  즉, 맵에 [키, 함수의 결과] 쌍을 저장합니다. <br> 
  이 코드는 merge 메서드의 전형적인 쓰임을 잘 보여주고 있습니다. <br> 
   
  깔끔해 보이는 코드지만 아직도 거추장스러운 부분이 남아 있습니다. <br>
  매개변수인 count와 incr은 크게 하는 일 없이 공간을 꽤 차지합니다. <br> 
  사실 이 람다는 두 인수의 합을 단순히 반환할 뿐입니다. <br> 
   
  자바 8이 되면서 Integer 클래스는 이 람다와 기능이 같은 정적 메서드 sum을 제공하기 시작했습니다. <br> 
  따라서 람다 대신 이 메서드의 참조를 전달하면 똑같은 결과를 더 보기 좋게 얻을 수 있습니다. <br> 
   
  map.merge(key, 1, Integer::sum);  
  
   
</details>

-----------------------
### Stream이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 이펙티브 자바] 
+ 스트림 API는 다량의 데이터 처리 작업(순차적이든 병렬적이든)을 돕고자 자바 8에 추가되었습니다. <br> 
  이 API가 제공하는 추상 개념 중 핵심은 두 가지입니다. <br> 
  
  그 첫번째인 스트림(stream)은 데이터 원소의 유한 혹은 무한 시퀀스(sequence)를 뜻합니다. <br> 
  두번째인 스트림 파이프라인(stream pipeline)은 이 원소들로 수행하는 연산 단계를 표현하는 개념입니다. <br> 
   
  스트림의 원소들은 어디로부터든 올 수 있다. <br> 
  대표적으로는 컬렉션, 배열, 파일, 정규표현식 패턴 매처(matcher), 난수 생성기, 혹은 다른 스트림이 있다. <br> 
  스트림 안의 데이터 원소들은 객체 참조나 기본 타입 값이다. <br>
  기본 타입 값으로는 int, long, double 이렇게 세 가지를 지원합니다. 
   
</details>


-----------------------

### Stream pipe line이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
   
+ 스트림 파이프라인은 소스 스트림에서 시작해 종단 연산(terminal operation)으로 끝나며, <br>
  그 사이에 하나 이상의 중간 연산(intermediate operation)이 있을 수 있다. <br> 
  각 중간 연산은 스트림을 어떠한 방식으로 변환(transform) 한다. <br> 
   
  예컨대 각 원소에 함수를 적용하거나 특정 조건을 마족 못하는 원소를 걸러낼 수 있다. <br>
  중간 연산들은 모두 한 스트림을 다른 스트림으로 변환하는데, <br> 
  변환된 스트림의 원소 타입은 변환 전 스트림의 원소 타입과 같을 수도 있고, 다를 수도 있다. <br> 
   
  종단 연산은 마지막 중간 연산이 내놓은 스트림에, 최후의 연산을 가한다. <br>
  원소를 정렬해 컬렉션에 담거나, 특정 원소 하나를 선택하거나, 모든 원소를 출력하는 식이다. 
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
   
+ 자바에서 Null처리는 == 혹은 Optional을 활용해서 할 수 있습니다. 
  단, ==으로 하는 방법의 단점은 프로그래머가 실수로 빼먹을 수 있다는 점입니다. 
</details>


-----------------------

### Optional에서 ofNullable 메소드는 어떤 경우에 사용되는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
   
+ ofNullable메소드는 전달되는 값이 null일 수 있는 경우에 사용합니다. 
</details>


-----------------------

### Optional에서 isPresent 메소드는 어떤 경우에 사용되는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
   
+ isPresent 메소드는 값이 존재하는지 확인하고 싶은 경우에 사용합니다. 
</details>


-----------------------

### Optional.of(10)과 같이 사용할 때의 단점은 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
   
+ boxing, unboxing이 자주 일어나서 성능상 좋지 않다는 점이 단점입니다. 
</details>


-----------------------

### Optional.get() 이란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
   
+ Optional에 있는 값을 가져오기 위해서 사용됩니다.  
</details>


-----------------------

### Optional orElseGet(Supplier)란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
   
+ Optional에 값이 있으면 가져오고, 없으면 ~~을 하라는 의미이다.  
</details>


-----------------------

### Java8에서 Date와 Time API가 등장한 이유는 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
   
+ (1) 기존의 java.util.date 객체는 mutable하기 때문에 Thread-safe하지 않다
  (2) 버그가 발생할 여지가 많았다.(타입 안정성이 없다)  
  (3) epoch 시간을 제공한다.  
</details>


-----------------------

### Instant.now()란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
   
+ 현재의 기계 시간을 리턴해준다. 
</details> 


-----------------------
