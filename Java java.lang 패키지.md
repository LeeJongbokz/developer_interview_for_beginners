
# Java java.lang 패키지 
<br>


### equals 메소드란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 자바의 정석] 
   
+ 매개변수로 객체의 참조변수를 받아서 비교하여 그 결과를 boolean 값으로 알려 주는 역할을 합니다. <br> 
  아래의 코드는 Object 클래스에 정의되어 있는 equals 메소드의 실제 내용입니다. <br> 
  
  ```
  public boolean equals(Object obj){
       return (this == obj);
  }
  ``` 
</details>

-----------------------

### Java에서 ==와 equals() 메서드의 차이점은?

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

### Boxing vs UnBoxing?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>


-----------------------

### equals(), hashCode()는 어떻게 오버라이딩 해야 하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 이펙티브 자바] 
   
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
