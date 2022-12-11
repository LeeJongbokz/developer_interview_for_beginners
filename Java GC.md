# GC
<br>

### GC란 무엇입니까? 

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 더 이상 참조되지 않는 객체를 모아서 정리하는 것을 의미합니다. 
</details>

-----------------------

### stop-the-world란 무엇입니까? 

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: https://d2.naver.com/helloworld/1329] 
   
+ stop-the-world란, GC를 실행하기 위해 JVM이 애플리케이션 실행을 멈추는 것을 의미합니다. <br>
  stop-the-world가 발생하면 GC를 실행하는 쓰레드를 제외한 나머지 쓰레드는 모두 작업을 멈춥니다. <br>
  GC 작업을 완료한 이후에야 중단했던 작업을 다시 시작합니다. <br> 
  어떤 GC 알고리즘을 사용하더라도 stop-the-world는 발생합니다. <br>
  대개의 경우 GC 튜닝이란 이 stop-the-world 시간을 줄이는 것입니다.  
</details>

-----------------------

### 가비지 컬렉터는 어떤 두 가지 가설하에 만들어졌고, 그 가설의 이름은 무엇인가? 

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: https://d2.naver.com/helloworld/1329] 
   
+ (1) 대부분의 객체는 금방 접근 불가능 상태(unreachable)가 됩니다. <br>
  (2) 오래된 객체에서 젊은 객체로의 참조는 아주 적게 존재합니다. <br>
  이러한 가설을 'weak generational hypothesis'라고 합니다. <br>
  이 가설의 장점을 최대한 살리기 위해서 HotSpot JVM에서는 크게 2개로 물리적 공간을 나누었습니다. <br>
  둘로 나눈 공간이 Young 영역과 Old영역입니다. <br> 
</details>

-----------------------

### GC의 Young 영역은 어떻게 구성됩니까? 그리고 각 영역의 처리절차는 어떻게 됩니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: https://d2.naver.com/helloworld/1329] 
   
+ Young 영역은 3개의 영역으로 나뉘는데, 하나의 Eden 영역과 두 개의 Survivor 영역으로 나뉩니다. <br> 
  각 영역의 처리절차를 순서에 따라 기술하면 다음과 같습니다. <br> 
  
  1) 새로 생성한 대부분의 객체는 Eden 영역에 위치합니다. <br> 
  2) Eden 영역에서 GC가 한 번 발생한 후, 살아남은 객체는 Survivor 영역 중 하나로 이동합니다. <br> 
  3) Eden 영역에서 GC가 발생하면, 이미 살아남은 객체가 존재하는 Survivor 영역으로 객체가 계속 쌓입니다. <br> 
  4) 하나의 Survivor 영역이 가득 차게 되면, 그 중에서 살아남은 객체를 다른 Survivor 영역으로 이동합니다. <br> 
     그리고 가득찬 Survivor 영역은 아무 데이터도 없는 상태가 됩니다 <br>
  5) 이 과정을 반복하다가 계속해서 살아 남아 있는 객체는 Old 영역으로 이동합니다. 
  
  이 절차를 확인해보면 알겠지만, Survivor 영역 중 한 영역은 반드시 비어 있는 상태로 남아 있어야 합니다. <br> 
  만약 두 Survivor 영역에 모두 데이터가 존재하거나, 두 영역 모두 사용량이 0이라면, <br>
  여러분의 시스템은 정상적인 상황이 아니라고 생각하면 됩니다. 
</details>

-----------------------


### Old 영역에 대한 GC는 대표적으로 무엇이 있습니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: https://d2.naver.com/helloworld/1329] 
   
+ Serial GC, Parellel GC, Parellel Old GC, CMS(Concurrent Mark&Sweep) GC, G1 GC가 있습니다. 
</details>

-----------------------

### Serial GC란 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: https://d2.naver.com/helloworld/1329] 
   
+ Serial GC는 Young 영역에서의 GC는 앞 절에서 설명한 방식을 사용합니다. <br> 
  Old 영역의 GC는 mark-sweep-compact라는 알고리즘을 사용합니다. <br> 
  이 알고리즘의 첫 단계는 Old 영역에 살아 있는 객체를 식별(Mark)하는 것입니다. <br> 
  그 다음에는 힙(heap)의 앞 부분부터 확인하여 살아 있는 것만 남깁니다. (Sweep) <br>
  마지막 단계에서는 각 객체들이 연속되게 쌓이도록 <br>
  힙의 가장 앞부분부터 채워서 객체가 존재하는 부분과 객체가 없는 부분으로 나눕니다. <br> 
  
  Serial GC는 적은 메모리와 CPU 코어 개수가 적을 때 적합한 방식입니다. <br> 
</details>

-----------------------

### Parallel GC란 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: https://d2.naver.com/helloworld/1329] 
+ Parallel GC는 Serial GC와 기본적인 알고리즘은 같습니다. <br> 
  그러나 Serial GC는 GC를 처리하는 스레드가 하나인 것에 비해, <br> 
  Parallel GC는 GC를 처리하는 쓰레드가 여러 개 입니다. <br> 
  그렇기 때문에 Parallel GC는 메모리가 충분하고, 코어의 개수가 많을 때 유리합니다. <br> 
  Parallel GC는 Throughput GC라고도 부릅니다. 
  
</details>

-----------------------

### Parallel Old GC란 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: https://d2.naver.com/helloworld/1329] 
+ Parallel Old GC는 JDK 5 update 6부터 제공한 GC 방식입니다. <br> 
  앞서 설명한 Parallel GC와 비교하여 Old 영역의 GC 알고리즘만 다릅니다. <br>
  이 방식은 Mark-Summary-Compaction 단계를 거칩니다. <br> 
  
  Summary 단계는 앞서 GC를 수행한 영역에 대해서 별도로 살아 있는 객체를 식별한다는 점에서 <br> 
  Mark-Sweep-Compaction 알고리즘의 Sweep 단계와 다르며,약간 더 복잡한 단계를 거칩니다. <br> 
</details>

-----------------------

### CMS 방식이란 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: https://d2.naver.com/helloworld/1329] 
  ![image](https://user-images.githubusercontent.com/8718430/205602525-ef16ef0b-2740-40b0-b769-00bb779e26c0.png)

+ CMS GC는 초기 Initial Mark 단계에서는 클래스 로더에서 가장 가까운 객체 중 살아 있는 객체만 찾는 것으로 끝냅니다. <br> 
  따라서 멈추는 시간은 매우 짤습니다. <br>
  그리고 Concurrent Mark 단계에서는 방금 살아있다고 확인한 객체에서 참조하고 있는 객체들을 따라가면서 확인한다. <br> 
  이 단계의 특징은 다른 스레드가 실행 중인 상태에서 동시에 진행된다는 것이다. <br> 
  
  그 다음 Remark 단계에서는 Concurrent Mark 단계에서 새로 추가되거나 참조가 끊긴 객체를 확인한다. <br> 
  마지막으로 Concurrent Sweep 단계에서는 쓰레기를 정리하는 작업을 실행한다. <br> 
  이 작업도 다른 스레드가 실행되고 있는 상황에서 진행한다. <br> 
  
  이러한 단계로 진행되는 GC 방식이기 때문에 stop-the-world 시간이 매우 짧다. <br> 
  모든 애플리케이션의 응답 속도가 매우 중요할 때, CMS GC를 사용하며, Low Latency GC라고도 부른다. <br> 
  
  그런데 CMS GC는 stop-the-world 시간이 짧다는 장점에 반해 다음과 같은 단점이 존재한다. <br> 
  (1) 다른 GC 방식보다 메모리와 CPU를 더 많이 사용한다. 
  (2) Compaction 단계가 기본적으로 제공되지 않는다. 
  
  따라서 CMS GC를 사용할 때에는 신중히 검토한 후에 사용해야 한다. <br> 
  그리고 조각난 메모리가 많아 Compaction 작업을 실행하면 <br> 
  다른 GC 방식의 stop-the-world 시간보다 stop-the-world 시간이 더 길기 때문에 <br>
  Compaction 작업이 얼마나 자주, 오랫동안 수행되는지 확인해야 한다. 
</details>

-----------------------


### G1 GC 방식이란 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: https://d2.naver.com/helloworld/1329] 
  ![image](https://user-images.githubusercontent.com/8718430/205602525-ef16ef0b-2740-40b0-b769-00bb779e26c0.png)

+ G1 GC는 바둑판의 각 영역에 객체를 할당하고 GC를 실행한다. <br> 
  그러다가, 해당 영역이 꽉 차면 다른 영역에서 객체를 할당하고 GC를 실행한다. <br> 
  즉, 지금까지 설명한 Young의 세 가지 영역에서 데이터가 Old영역으로 이동하는 단계가 <br>
  사라진 GC 방식이라고 이해하면 된다. <br>
  G1 GC는 장기적으로 말도 많고 탈도 많은 CMS GC를 대체하기 위해서 만들어졌다. <br> 
  
  G1 GC의 가장 큰 장점은 성능이다. 지금까지 설명한 어떤 GC 방식보다도 빠르다. 
</details>

-----------------------
