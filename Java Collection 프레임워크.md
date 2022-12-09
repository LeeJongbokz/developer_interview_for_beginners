# Java Collection 프레임워크
<br>

-----------------------

### HashMap vs HashTable vs ConcurrentHashMap의 차이점은?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: https://tecoble.techcourse.co.kr/post/2021-11-26-hashmap-hashtable-concurrenthashmap/] 
+ (1) HashMap 
  - key와 value에 null을 허용합니다 <br>
  - 동기화를 보장하지 않습니다. <br> 
  -> HashMap은 Thread-safe하지 않아, 싱글 스레드 환경에서 사용하는 것이 좋습니다. <br> 
     한편, 동기화를 처리하지 않기 때문에, 데이터를 탐색하는 속도가 빠릅니다. <br>
     결국 HashTable과 ConcurrentHashMap보다 데이터를 찾는 속도는 빠르지만, <br>
     신뢰성과 안정성은 떨어집니다. 
   
  (2) HashTable
  - key와 value에 null을 허용하지 않습니다. 
  - 동기화를 보장합니다. 
  -> HashTable은 Thread-safe하기 때문에, 멀티 스레드 환경에서 사용할 수 있습니다. <br> 
     이는 데이터를 다루는 메소드(get(), put(), remove()) 등에 synchronized 키워드가 붙어 있습니다. <br> 
     해당 키워드는 메소드를 호출하기 전에 스레드간 동기화 락을 겁니다. <br> 
     그래서 멀티 스레드 환경에서도 데이터의 무결성을 보장합니다. <br> 
     그러나 스레드 간 동기화 락은 매우 느린 동작이라는 단점이 있습니다. <br> 
   
  (3) ConcurrentHashMap
  - key와 value에 null을 허용하지 않습니다. 
  - 동기화를 보장합니다. 
  -> ConcurrentHashMap은 Thread-safe하기 때문에, 멀티 스레드 환경에서 사용할 수 있습니다. <br> 
     이 구현체는 HashMap의 동기화 문제를 보완하기 위해 나타났습니다. <br> 
     동기화 처리를 할 때, 어떤 Entry를 조작하는 경우에, 해당 Entry에 대해서만 락을 겁니다. <br> 
     그래서 HashTable보다 데이터를 다루는 속도가 빠릅니다. <br>
     즉, Entry 아이템별로 락을 걸어 멀티 스레드 환경에서의 성능을 향상시킵니다. 
</details>

-----------------------

### Java Map 인터페이스 구현체의 종류는?
<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ . 
</details>

-----------------------

### Java Set 인터페이스 구현체의 종류는?
<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ . 
</details>

-----------------------

### Java List 인터페이스 구현체의 종류는?
<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ . 
</details>

-----------------------
