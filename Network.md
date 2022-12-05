# Network
<br>


-----------------------

### CORS란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>

-----------------------

### CSRF란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ CSRF는 Cross Site Request Forgery의 줄임말로,  
  사용자가 위조된 코드가 포함된 페이지에 접근하면,
  사용자에게 스크립트가 전송되고, 브라우저에 의해 스크립트가 실행되는데,
  스크립트가 사용자를 대신해 동작을 실행하는 공격을 의미합니다. 
</details>

-----------------------

### XSS란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 
</details>


-----------------------

### DNS란? DNS는 어떻게 동작하나요? 
 
<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 인터넷 사용자가 호스트를 지칭할 때는 문자형의 도메인 이름으로 주소를 표현합니다. <br> 
  그러므로 도메인 이름을 네트워크에서 사용하려면 IP 주소로 변환하는 과정이 필요합니다. <br> 
  
  DNS는 계층 구조를 지원하는 도메인 기반의 주소 표기 방법을 위한 분산 데이터베이스 시스템으로, <br>
  기본 목적은 도메인 이름에서 IP 주소를 얻는 것입니다. <br> 
  
  예를 들어, IP 주소를 원하는 응용 프로그램은 도메인 이름을 매개변수로 하여 해석기(Resolver)를 호출합니다. <br> 
  해석기는 UDP를 이용해 자신이 위치한 지역의 DNS 네임 서버에 변환을 요청하여 호스트의 IP 주소를 얻습니다. <br> 
   
  유닉스 시스템에서 지원하는 nslookup 명령은 DNS를 이용해 주소 변환 요구를 수행하는 대화형 프로그램입니다. <br>
  다음의 예처럼 도메인 이름이 information.korea.co.kr인 호스트의 IP 주소를 얻으려면 nslookup을 다음과 같이 실행합니다. <br>
   
  실행 결과는 사용자가 로그인한 유닉스 시스템의 환경 설정에서 DNS 서버가 server.korea.co.kr이라 가정한 경우입니다. <br> 
  따라서 nslookup 프로그램은 이 서버에 information.korea.co.kr의 IP 주소를 요청합니다. <br> 
  그 결과 DNS 서버의 도메인 이름(server.korea.co.kr)과 IP 주소(211.223.201.30)가 반환됩니다. <br> 
   
  DNS 서버 server.korea.co.kr은 정해진 방법으로 IP 주소를 찾아 nslookup에 결과를 돌려주므로, <br>
  nslookup이 화면에 출력한 결과로 information.korea.co.kr의 IP주소가 <br>
  211.223.201.29임을 알 수 있습니다. <br> 
   
  DNS는 도메인 네임 스페이스, 네임 서버, 해석기라는 세 가지 요소로 구성됩니다. <br>  
</details>

-----------------------

### 도메인 네임 스페이스란 무엇입니까?  
 
<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 도메인 네임 스페이스는 트리 구조의 네임 스페이스를 비롯해 데이터에 대한 이름 관련 규칙을 정의합니다. <br> 
  도메인 네임 스페이스의 트리에 연결된 호스트는 자원 레코드(Resource Record)라는 정보 집합체로 표현됩니다. <br> 
  DNS의 정보 문의 과정은 이 집합체에서 특정 유형의 정보를 얻는 과정입니다. <br> 
  예를 들어, 인터넷에서 특정 도메인의 이름을 사용하는 호스트의 IP 주소 자원을 요청하는 질의에 대해 IP 주소를 반환합니다. <br>  
</details>

-----------------------

### 네임 서버란?  
 
<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 네임서버는 네임 스페이스의 트리 구조와 트리에 보관된 정보 집합체를 관리하는 프로그램입니다. <br> 
  일반적으로 자신이 관리하는 도메인 공간에 관한 정보를 책임지며, 전체 도메인 구조의 다른 부분 정보를 제공하기 위한 <br>
  네임 서버 포인터를 가지고 있습니다. 
</details>

-----------------------

### 해석기란?  
 
<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 해석기는 네임 서버로부터 클라이언트의 요청 정보를 얻어낸느 프로그램입니다. <br> 
  최소 하나 이상의 네임 서버와 접촉하며, 네임 서버의 정보를 이용해 응용 프로그램의 질의에 응답한다. <br> 
  처음 접촉한 네임 서버에 도메인 정보가 없으면 다른 네임 서버에 접속해 계속 질의한다. <br> 
</details>

-----------------------


### SSH란? 
 
<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
[참고: https://library.gabia.com/contents/infrahosting/9002/] 
   
+ Secure Shell의 줄임말로, 원격 호스트에 접속하기 위해 사용되는 보안 프로토콜입니다. 
</details>
