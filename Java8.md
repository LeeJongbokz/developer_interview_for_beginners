# Java8
<br>



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
