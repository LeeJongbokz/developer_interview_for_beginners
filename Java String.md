# Java String
<br>


### String클래스의 가장 큰 특징은?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 자바의 정석] 
+ String 클래스의 가장 큰 특징은 변경 불가능한(immutable) 클래스라는 점입니다. <br>
  String 클래스에는 문자열을 저장하기 위해서 문자형 배열 참조변수(char[]) value를 인스턴스 변수로 정의해놓고 있습니다. <br>
  인스턴스 생성 시 생성자의 매개변수로 입력받는 문자열은 이 인스턴스 변수(value)에 문자형 배열(char[])로 저장됩니다. <br> 
   
  한 번 생성된 String 인스턴스가 갖고 있는 문자열은 읽어 올 수만 있고, 변경할 수는 없습니다. <br> 
  예를 들어, 아래의 코드와 같이 '+'연산자를 이용해서 문자열을 결합하는 경우 인스턴스 내의 문자열이 바뀌는 것이 아니라 <br> 
  새로운 문자열("ab")이 담긴 String 인스턴스가 생성됩니다. 
   
  String a = "a";
  String b = "b";
  a = a + b; 
   
  이처럼 덧셈연산자 '+'를 사용해서 문자열을 결합하는 것은 매 연산 시 마다 새로운 문자열을 가진 String 인스턴스가 생성되어 <br>
  메모리 공간을 차지하게 되므로, 가능한 한 결합횟수를 줄이는 것이 좋다. <br> 
  문자열 간의 결합이나 추출 등 문자열을 다루는 작업이 많이 필요한 경우네는 String 클래스 대신 <br> 
  StringBuffer 클래스를 사용하는 것이 좋다. <br>
  StringBuffer 인스턴스에 저장된 문자열은 변경이 가능하므로, 하나의 StringBuffer 인스턴스만으로도 문자열을 다루는 것이 가능하다. 
</details>

-----------------------


### String vs StringBuilder vs StringBuffer의 차이점은?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 이펙티브 자바] 
+ 
   
  
</details>

-----------------------

### new String()과 ""의 차이점은?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: 자바의 정석] 
+ String 클래스의 생성자를 이용한 경우에는 new 연산자에 의해서 메모리 할당이 이루어지기 때문에, <br>
  항상 새로운 인스턴스가 생성됩니다. <br> 
  그러나 문자열 리터럴은 이미 존재하는 것을 재사용하는 것입니다. 
   
  
</details>
