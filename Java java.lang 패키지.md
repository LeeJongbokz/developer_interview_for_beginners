
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
  위의 코드에서 알 수 있듯이 두 객체의 같고 다름을 참조변수의 값으로 판단합니다. <br> 
  그렇기 때문에 서로 다른 두 객체를 equals 메서드로 비교하면 항상 false를 결과로 얻게 됩니다. <br> 
   
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
   
[참고: 자바의 정석]    

+ 이 메서드는 해싱(hashing) 기법에 사용되는 해시 함수(hash function)을 구현한 것입니다. <br> 
  해싱은 데이터관리기법 중의 하나인데, 다량의 데이터를 저장하고 검색하는데 유용합니다. <br> 
  해시함수는 찾고자 하는 값을 입력하면, 그 값이 저장된 위치를 알려주는 해시 코드(hash code)를 반환합니다.<br>
  
  일반적으로 해시코드가 같은 두 객체가 존재하는 것이 가능하지만, <br> 
  Object 클래스에 정의된 hashCode 메서드는 객체의 주소값으로 해시코드를 만들어 반환하기 때문에<br>
  32 bit JVM에서는 서로 다른 두 객체는 결코 같은 해시코드를 가질 수 없었지만, <br>
  64 bit JVM에서는 8 byte 주소값으로 해시코드(4 byte)를 만들기 때문에 해시코드가 중복될 수 있습니다. 
   
</details>


-----------------------
### equals를 재정의할 때, 반드시 hashCode도 재정의해야 하는데 이유는 무엇인가요?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>

-----------------------

### 얕은 복사와 깊은 복사의 차이점은?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ clone()은 단순히 객체에 저장된 값을 그대로 복제할 뿐, <br> 
  객체가 참조하고 있는 객체까지 복제하지는 않습니다. <br> 
  객체 배열을 clone()으로 복제하는 경우에는 원본과 복제본이 같은 객체를 공유하므로 완전한 복제라고 보기는 어렵습니다. <br> 
  이러한 복제(복사)를 얕은 복사라고 합니다. <br>
  얕은 복사에서는 원본을 변경하면 복사본도 영향을 받습니다. <br> 
   
  반면에, 원본이 참조하고 있는 객체까지 복제하는 것을 깊은 복사라고 합니다. <br> 
  깊은 복사에서는 원본과 복사본이 서로 다른 객체를 참조하기 때문에 원본의 ㅂ녀경이 복사본에 영향을 미치지 않습니다. <br> 
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
### 래퍼(wrapper) 클래스란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 자바의 정석] 
   
+ 때로는 기본형(primitive type) 변수도 어쩔 수 없이 객체로 다뤄야 하는 경우가 있습니다. <br> 
  예를 들면, 매개변수로 객체를 요구할 때, 기본형 값이 아닌 객체로 저장해야 할 때, <br> 
  객체간의 비교가 필요할 때 등등의 경우에는 기본형 값들을 객체로 변환하여 작업을 수행해야 합니다. <br> 
   
  이 때, 사용되는 것이 래퍼(wrapper) 클래스입니다. 8개의 기본형을 대표하는 8개의 래퍼클래스가 있는데, <br> 
  이 클래스들을 이용하면 기본형 값을 객체로 다룰 수 있습니다. 
</details>

-----------------------
