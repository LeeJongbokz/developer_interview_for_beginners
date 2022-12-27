# GC
<br>

### GC란 무엇입니까? 

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 더 이상 참조되지 않는 객체를 모아서 정리하는 것을 의미합니다. 
   

[참고: JVM Performance Optimizing p.25]    
   
+ 본 절에서는 HotSpot JVM의 Garbage Collection에 대한 기본적인 동작 방식과 Internal한 내용이 포함되어 있다. <br>
  본문 내용을 통해 WAS의 Suspend 현상과 애플리케이션 Thread, Garbage Collection Thread 간의 경합에 대해 이해하고, <br> 
  나아가 특정 환경에 적합한 Garbage Collector를 선택할 수 있는 기본적인 지식을 제공할 목적이다. <br> 
   
  앞서 본 Garbage Collection에 대한 JVM Speculation을 부연 설명하자면, 이미 할당된 Memory는 Garbage Collection(이하 GC)에 의해 <br> 
  해제가 되는데 이 때 Garbage는 Heap과 Method Area에서 사용되지 않는 Object를 의미합니다. <br> 
  그리고 소스상의 close()는 Object 사용중지 의사표현일 뿐, Object를 Memory에서 삭제하겠다는 의미가 아닙니다. <br> 
  개발자는 System.GC()를 명시적으로 사용하여 GC를 발생시킬 수 있지만, 이 경우에는 Full GC가 발생합니다. <br> 
   
   
   
</details>

-----------------------

### GC로 인한 문제점이 무엇입니까? 

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 더 이상 참조되지 않는 객체를 모아서 정리하는 것을 의미합니다. 
   

[참고: JVM Performance Optimizing p.25]    
   
+ GC라는 자동화 메커니즘으로 인해 프로그래머는 직접 Memory를 핸들링 할 필요가 없게 되었습니다. <br> 
  더불어 잘못된 Memory 접근으로 인한 Crash 현상의 소지도 없어지게 되었으니, 더 없이 편리한 기능이 아닐 수 없습니다. <br> 
  그러나 GC는 명시적인 Memory 해제보다 느리며, GC 순간 발생하는 Suspend Time으로 인해 다양한 문제를 야기시킵니다. <br> 
  시스템의 성격마다 Suspend Time 허용치는 각각 다르겠지만, GC 튜닝을 실시할 경우 통상 애플리케이션 최적화 이후(생성 오브젝트 최소화 등) <br> 
  본격적인 GC 튜닝을 진행합니다. <br>  
   

</details>

-----------------------

### Root Set과 Garbage란 무엇입니까? 

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

[참고: JVM Performance Optimizing p.26]    
   
+ Garbage Collection은 말 그대로 Garbage를 모으는 작업인데, 여기서 Garbage란 사용되지 않는 Object를 말합니다. <br>
  좀 더 명확히 설명하면 Object의 사용 여부는 Root Set과의 관계로 판단하게 되는데, <br> 
  Root Set에서 어떤 식으로든 Reference 관계가 있다면, Reachable Object라고 하며 <br>
  이를 현재 사용하고 있는 Object로 간주하게 됩니다. <br> 
   
  Root Set은 광의적 개념으로서 좀 더 구체적으로 말하면 아래와 같이 3가지 참조 형태를 통해 Reachable Object를 판별합니다. <br> 
  (1) Local Variable Section, Operand Stack에 Object의 Reference 정보가 있다면 Reachable Object이다. <br> 
  (2) Method Area에 로딩된 클래스 중 constant pool에 있는 Reference 정보를 토대로 Thread에서 직접 참조하진 않지만, <br> 
      constant pool을 통해 간접 link하고 있는 Object는 Reachable Object이다. <br> 
  (3) 아직 Memory에 남아 있으며 Native Method Area로 넘겨진 Object의 Reference가 JNI 형태로 참조 관계가 있는 Object는 <br>
      Reachable Object이다. <br> 
   
  위의 3가지 경우를 제외하면 모두 GC 대상이 됩니다. <br>   
   
</details>

-----------------------

### Reachable but not Live Object란 무엇입니까? 

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

[참고: JVM Performance Optimizing p.27]    
   
+ 
   ```
   import java.util.*;
   class Main{
         public static void main(String[] args){
                Leak lk = new Leak();
                for(int a=0; a<9000000; a++){
                      lk.addList(a);
                      lk.removeStr(a);                    
                }
         }
   }
                                        
                                        
   class Leak{
       ArrayList lst = new ArrayList();
       public void addList(int a){
             lst.add("가나다라마바사아자차카타파하" + a);                                
       }
       public void removeStr(int i){
             Object obj = lst.get(i);
             obj = null;                           
       }                
   }
   ```
                                        
   이 샘플 소스는 Collection 객체인 ArrayList에 String Object를 넣고 바로 제거하려는 의도로 만들어진 코드입니다. <br> 
   제거하기 위해 만들어진 removeStr() 메소드가 Object Reference 변수를 찾아 null로 치환하는 방식을 사용하였습니다. <br> 
   
   그러나 이 소스를 컴파일하여 실행하면 OutOfMemoryException이 발생하여 프로그램이 비정상 종료하게 됩니다. <br> 
   그 이유는 obj로 받은 것은 String 객체가 아니라 String 객체로 접근하는 Reference 값이기 때문입니다 <br>
   
   주민등록이 말소되었다고 사람 자체가 없어지지 않는 것과 마찬가지로 Reference가 null로 치환되었다고 해서 <br>
   ArrayList에 들어가 있는 String 객체가 사라지지 않게 됩니다. <br> 
   하지만 이 String 객체는 이제 사용되지 않을 것입니다. <br> 
   이것이 바로 "Reachable but not Live" 객체인 것입니다. <br> 
   이러한 객체가 많아지면 우리는 Heap에 Memory Leak이 발생했다고 표현합니다. <br> 
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

### Hotspot JVM의 Heap 구조는 어떻게 되는가? 

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: JVM Performance Optimizing p.20~21] 
   
+ HotSpot JVM의 Heap 구조에 대해 알아보고자 한다. <br> 
  HotSpot JVM은 익히 알려져 있듯이 크게 Young Generation과 Old Generation으로 나누어져 있다. <br> 
  
  Young Generation은 Eden 영역과 Survivor 영역으로 구성되는데, <br> 
  Eden 영역은 Object가 Heap에 최초로 할당되는 장소이며, Eden 영역이 꽉 차게 되면 Object의 참조 여부를 따져 <br> 
  만약 참조가 되어 있는 Live Object이며 Survivor 영역으로 넘기고, 참조가 끊어진 Garbage Object이면 그냥 남겨 놓는다. <br> 
  모든 Live Object가 Survivor 영역으로 넘어가면 Eden 영역을 모두 청소(Scanvenge)한다. <br> 
   
  Survivor 영역은 말 그대로 Eden 영역에서 살아남은 Object들이 잠시 머무르는 곳이다. <br> 
  이 Survivor 영역은 두 개로 구성되는데(Survivor1, Survivor2) Live Object를 대피시킬 때는, 하나의 Survivor 영역만 사용하게 된다. <br> 
  이러한 전반의 과정을 Minor GC라고 한다. <br> 
  자세한 사항은 Garbage Collection 부분에서 상세히 다루기로 한다. <br> 
   
  Young Generation에서 Live Object로 오래 살아남아 성숙된 Object는 Old Generation으로 이동하게 된다. <br> 
  여기서 성숙된 Object란 의미는 애플리케이션에서 특정 회수 이상 참조되어 기준 Age를 초과한 Object를 말한다. <br> 
  
  Old Generation 영역은 새로 Heap에 할당되는 Object가 들어오는 것이 아니라, <br> 
  비교적 오랫동안 참조가 되어 이용되고 있고, 앞으로도 계속 사용될 확률이 높은 Object들을 저장하는 영역이다. <br> 
  이러한 Promotion 과정 중 Old Generation의 메모리도 충분하지 않으면 해당 영역에도 GC가 발생하는데 <br>
  이를 가리켜 Full GC(Major GC)라고 한다. <br> 
   
  Perm 영역은 보통 Class의 Meta 정보나 Method의 Meta 정보, STatic 변수와 상수 정보들이 저장되는 공간으로 <br> 
  흔히 메타데이터 저장 영역이라고도 한다. <br> 
  이 영역은 Java 8 부터는 Native 영역으로 이동하여 Metaspace 영역으로 변경되었다. <br>
  (다만, 기존 Perm 영역에 존재하던 Static Object는 Heap 영역으로 옮겨져서 GC의 대상이 최대한 될 수 있도록 하였다.) <br> 
   
  현재 가장 많이 사용중인 Java 7과 최신 Java8의 구조적인 측면에서 변경 사항을 중심으로 좀 더 비교 설명하고자 한다. <br> 
  
  최근 Java 8에서 JVM 메모리 구조적인 개선 사항으로 Perm 영역이 아닌 Metaspace 영역으로 전환되고, 기존 Perm 영역은 사라지게 되었다. <br> 
  Metaspace 영역은 Heap이 아닌 Native 메모리 영역으로 취급하게 된다. <br>
  (Heap 영역은 JVM에 의해 관리된 영역이며, Native 메모리는 OS레벨에서 관리하는 영역으로 구분된다.) <br> 
  Metaspace가 Native 메모리를 이용함으로써 개발자는 영역 확보의 상한을 크게 의식할 필요가 없어지게 되었다. <br>  
  
   
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
