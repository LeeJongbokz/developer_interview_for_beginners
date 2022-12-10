# Java Collection 프레임워크
<br>


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
[참고: 자바의 정석] 
   
+ HashMap, HashTable, ConcurrentHashMap, TreeMap 등이 있습니다.  
</details>

-----------------------

### HashMap 클래스의 특징은 무엇입니까?
<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 자바의 정석] 
   
+ Map을 구현했으므로 앞에서 살펴본 Map의 특징, 키(key)와 값(value)을 묶어서 <br> 
  하나의 데이터(entry)로 저장한다는 특징을 갖습니다. <br> 
  그리고 해싱(hashing)을 사용하기 때문에 많은 양의 데이터를 검색하는데 있어서 뛰어난 성능을 보입니다. <br> 
</details>

-----------------------

### 해싱(hashing)이란 무엇입니까?
<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 자바의 정석] 
   
+ 해싱이란 해시 함수(hash function)를 이용해서 데이터를 해시 테이블(hash table)에 저장하고 검색하는 기법을 말합니다. <br> 
  해시함수는 데이터가 저장되어 있는 곳을 알려주기 때문에 다량의 데이터 중에서도 원하는 데이터를 빠르게 찾을 수 있습니다. <br> 
  
  해싱을 구현한 컬렉션 클래스로는 HashSet, HashMap, HashTable 등이 있습니다. <br> 
  HashTable은 컬렉션 프레임웍이 도입되면서 HashMap으로 대체되었으나 이전 소스와의 호환성 문제로 남겨 두고 있습니다. <br> 
  가능하면 HashTable 대신 HashMap을 사용하는 것이 좋습니다. <br> 
   
  저장할 데이터의 키를 해시함수에 넣으면 배열의 한 요소를 얻게 되고, <br>
  다시 그 곳에 연결되어 있는 링크드 리스트에 저장하게 됩니다. 
  
</details>

-----------------------

### 해시 충돌(hash collision)이란 무엇입니까?
<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: https://d2.naver.com/helloworld/831311] 
   
+ 동일하지 않은 어떤 객체 X와 Y가 있을 때, 즉, X.equals(Y)가 '거짓'일 때, X.hashCode() != Y.hashCode()가 같지 않다면, <br> 
  이 때 사용하는 해시 함수는 완전한 해시 함수(perfect hash functions)라고 합니다. <br> 
   
  HashMap은 기본적으로 각 객체의 hashCode() 메서드가 반환하는 값을 사용하는데, 결과 자료형은 int입니다. <br> 
  32비트 정수 자료형으로는 완전 해시 함수를 만들 수 없습니다. <br> 
  논리적으로 생성 가능한 객체의 수가 2^32보다 많을 수 있기 때문이며, <br> 
  또한 모든 HashMap 객체에서 O(1)을 보장하기 위해 랜덤 접근이 가능하게 하려면 <br> 
  원소가 2^32인 배열을 모든 HashMap이 가지고 있어야 하기 때문입니다. <br> 
   
  따라서 HashMap을 비롯한 많은 해시 함수를 이용하는 associative array 구현체에서는 메모리를 절약하기 위하여 <br> 
  실제 해시 함수의 표현 정수 범위보다 작은 M개의 원소가 있는 배열만을 사용합니다. <br> 
  따라서 다음과 같이 객체에 대한 해시 코드의 나머지 값을 해시 버킷 인덱스 값으로 사용합니다. <br> 
   
  ```
  int index = X.hashCode() % M;  
  ```
   
  이 코드와 같은 방식을 사용하면, 서로 다른 해시 코드를 가지는 서로 다른 객체가 1/M의 확률로 같은 해시 버킷을 사용하게 됩니다. <br> 
  이는 해시 함수가 얼마나 해시 충돌을 회피하도록 잘 구현되었느냐에 상관없이 발생할 수 있는 또 다른 종류의 해시 충돌입니다. 
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
