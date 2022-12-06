# Java 스레드
<br>

-----------------------

### 스레드란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 이펙티브 자바] 
+ 스레드는 여러 활동을 동시에 수행할 수 있게 해줍니다. <br> 
  하지만 동시성 프로그래밍은 단일 스레드 프로그래밍보다 어렵습니다. <br> 
  잘못될 수 있는 일이 늘어나고, 문제를 재현하기도 어려워지기 때문입니다. <br> 
   
  그렇다고 동시성 프로그래밍으로부터 언제까지나 도망 다닐 수는 없습니다. <br>
  자바 플랫폼 자체에 내재되어 있을 뿐만 아니라, <br>
  오늘날 어디서나 쓰이는 멀티코어 프로세서의 힘을 제대로 활용하려면 <br> 
  반드시 내 것으로 만들어야 하는 기술이기 때문입니다. <br>
   
  
</details>

-----------------------

### Synchronized 키워드란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 이펙티브 자바] 
+ synchronized 키워드는 해당 메서드나 블록을 한 번에 한 스레드씩 수행하도록 보장합니다. <br>
  많은 프로그래머가 동기화를 배타적 실행, 즉 한 스레드가 변경하는 중이라서 <br>
  상태가 일관되지 않은 순간의 객체를 다른 스레드가 보지 못하게 막는 용도로만 생각합니다. <br> 
   
  먼저 이 관점에서 얘기해봅니다. 한 객체가 일관된 상태를 가지고 생성되고, <br>
  이 객체에 접근하는 메서드는 그 객체에 락(lock)을 겁니다. <br>
  락을 건 메서드는 객체의 상태를 확인하고 필요하면 수정합니다. <br>
  즉, 객체를 하나의 일관된 상태에서 다른 일관된 상태로 변화시킵니다. <br> 
  동기화를 제대로 사용하면 어떤 메서드도 이 객체의 상태가 일관되지 않은 순간을 볼 수 없을 것입니다. <br> 
   
  맞는 설명이지만, 동기화에는 중요한 기능이 하나 더 있습니다. <br> 
  동기화 없이는 한 스레드가 만든 변화를 다른 스레드에서 확인하지 못할 수 있습니다. <br> 
  동기화는 일관성이 깨진 상태를 볼 수 없게 하는 것은 물론, <br>
  동기화된 메서드나 블록에 들어간 스레드가 같은 락의 보호하에 수행된 <br>
  모든 이전 수정의 최종 결과를 보게 해줍니다. <br> 
   
</details>

-----------------------


### 하나의 프로세스가 가질 수 있는 스레드의 상한은 어떻게 결정되나요?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 스레드는 작업을 수행하는데 개별적인 호출 스택(call stack)을 필요로 합니다. <br> 
  따라서 프로세스의 메모리 한계에 따라, 프로세스가 가질 수 있는 스레드의 상한이 결정됩니다. 
</details>

-----------------------


### 멀티 태스킹이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 하나의 CPU가 여러 개의 프로세스를 동시에 실행할 수 있는 특성을 의미합니다. 
</details>

-----------------------


### 멀티 스레딩이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 하나의 프로세스 내에서 여러 개의 스레드가 동시에 작업을 수행하는 것을 의미합니다. <br>
  단, CPU의 코어는 한 번에 한 가지 작업만 수행하므로, <br>
  실제로 동시에 처리되는 작업의 수는 코어의 개수와 일치합니다. 
</details>

-----------------------

### Concurrent 소프트웨어란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 동시에 여러 작업을 할 수 있는 소프트웨어를 의미합니다. 
</details>

-----------------------

### 자바에서 멀티 스레드를 구현하기 위한 방법에는 무엇이 있습니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Thread 클래스를 상속 받거나, Runnable 인터페이스를 구현해야 합니다. 
</details>

-----------------------

### 자바에서 스레드 실행과 관련된 특징은 무엇이 있습니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 스레드의 실행 순서를 보장하지 못한다는 점입니다. 
</details>

-----------------------

### 스레드의 sleep 메소드란 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 현재 스레드를 대기시키는 것을 의미합니다.  
  sleep 메소드를 실행하면 다른 스레드에 우선권이 넘어갑니다. 
</details>

-----------------------

### 스레드의 interrupt 메소드란 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 대기 중인 메소드를 깨우는 것을 의미합니다. 
</details>

-----------------------


### 스레드의 join 메소드란 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 
</details>

-----------------------


### Executors란 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 스레드를 만들고 관리하는 작업을 담당하는 고수준의 API를 의미합니다. 
</details>

-----------------------

### ExecutorService란 무엇입니까? ExecutorService 내부에 무엇이 존재합니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Executor를 상속 받은 인터페이스를 의미합니다. <br> 
  ExecutorService 내부에는 스레드 풀이 존재합니다.  
</details>

-----------------------

### 스레드 풀의 장점은 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 스레드 풀은 스레드를 생성하는 비용이 적게 든다는 점이 장점입니다. 
</details>

-----------------------

### ExecutorService의 submit()과 shutdown()은 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ submit()은 스레드의 실행을 위한 값을 전달하는 것을 의미합니다. <br> 
  shutdown()은 ExecutorService를 종료하는 것을 의미합니다. 
</details>

-----------------------

### ExecutorService의 Blocking Queue는 왜 필요합니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 스레드 풀에 스레드들이 모두 사용중일 때, 요청을 대기시키기 위해서 필요합니다. 
</details>

-----------------------

### Fork/join 프레임워크란 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ ExecutorService의 구현체로서, 멀티 프로세서를 사용하며, 애플리케이션 개발할 때 유용합니다. 
</details>

-----------------------

### Runnable과 Callable의 차이점은 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Runnable은 반환값이 없지만, Callable은 반환값이 존재한다는 점이 차이점입니다. 
</details>

-----------------------

### Future란 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 비동기적인 작업의 현재 상태를 조회하거나 작업을 가져올 수 있는 객체를 의미합니다. 
</details>

-----------------------

### ExecutorService의 invokeAll()이란 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 여러 개의 Callable을 한 번에 담는 메소드를 의미합니다. 
  즉, 여러 작업을 동시에 실행 가능하게 해줍니다. 
</details>

-----------------------

### ExecutorService의 invokeAny()란 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 여러 작업 중 하나라도 먼저 응답이 오면 끝내는 것을 의미합니다. 
  즉, 여러 작업 중 가장 짧은 작업만큼의 시간이 걸리며,
  블로킹 콜에 속합니다. 
</details>

-----------------------

### CompletableFuture란 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 자바에서 비동기 프로그래밍을 가능하게 하는 인터페이스를 의미합니다.  
</details>

-----------------------

### Future의 단점은 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 1) 예외 처리 API를 제공하지 않는다
  2) 여러 Future를 조합할 수 없다
  3) 블로킹 코드(get())를 사용하지 않고서는 작업이 끝났을 때, 콜백을 실행할 수 없다. 
</details>

-----------------------

### CompletableFuture에서 어떻게 비동기로 작업을 실행하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 리턴값이 없는 경우는 runAsync()를 사용하고,
  리턴값이 있는 경우는 supplyAsync()를 사용합니다. 
</details>

-----------------------

### CompletableFuture에서 어떻게 콜백을 제공하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ thenApply(Function)는 리턴값을 받아서 다른 값으로 바꾸는 콜백입니다. <br> 
  thenAccept(Consumer)는 리턴값을 또 다른 작업으로 처리하는 콜백입니다. 
</details>

-----------------------
