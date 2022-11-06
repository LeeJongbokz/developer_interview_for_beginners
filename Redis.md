# Redis
<br>

-----------------------

### Redis vs Memcached?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
 
   1. Redis
  - Redis는 캐시 솔루션 + 저장소입니다. <br>
  - Redis는 Key-value, List, Hash, Set, Sorted Set과 같은 다양한 자료구조를 지원합니다. <br>
  - Redis는 싱글 스레드로 동작합니다. <br>
  - Redis는 트랜잭션, 스냅샷, Replication, Pub/sub, Lua Scripting과 같은 기능을 지원합니다. <br>
   
   2. Memcached 
  - Memcached는 캐시 솔루션입니다.
  - Memcached는 Key-value 자료구조를 지원합니다.
  - Memcached는 멀티 스레드로 동작합니다. 
</details>

-----------------------

### Redis Single thread는 어떤 식으로 동작하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+  
</details>

-----------------------


### Redis Pub-sub은 어떤 식으로 동작하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Pub-sub 패턴이란, Publisher들이 특정한 subscriber를 고려하지 않고 메시지를 생성한 후, <br>
  Publish된 메시지들이 channel로 분류된 후, <br>
  Subscribers는 자신이 관심 있는 channel에 있는 메시지만 받아보는 방식을 의미합니다.<br>
   
  Pub-sub 패턴의 장점은 높은 확장성과 다이내믹한 네트워크 토폴로지를 가능하게 한다는 점입니다.  
</details>

-----------------------

