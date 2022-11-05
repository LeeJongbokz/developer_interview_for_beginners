
# Java 입출력
<br>

-----------------------

### 자바 입출력에서 스트림이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 스트림이란 데이터를 운반하는데 사용되는 연결 통로를 의미합니다. 
</details>

-----------------------

### 자바 입출력에서 스트림의 구성적인 특징은?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 스트림은 먼저 보낸 데이터를 먼저 받는 FIFO 구조로 되어 있습니다. 
</details>

-----------------------

### 입력과 출력을 동시에 수행하려면 어떤 스트림이 필요한가요?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 입력 스트림(Input Stream), 출력 스트림(Output Stream)이 필요합니다. 
</details>

-----------------------

### 자바 입출력에서 스트림은 어떤 단위로 데이터를 전송하나요?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 스트림은 기본적으로 바이트 단위로 데이터를 전송합니다. 이를 바이트 스트림이라고 합니다.<br> 
  바이트 기반이라 함은 입출력의 단위가 1byte라는 뜻입니다.<br>
  ex) InputStream, OutputStream <br>
   
  자바에서는 한 문자를 의미하는 char형이 1byte가 아니라 2byte이기 때문에 <br>
  바이트기반의 스트림으로 2byte인 문자를 처리하는데 어려움이 있습니다. <br>
  따라서 이 점을 보완하기 위해 문자 기반의 스트림이 제공됩니다. <br>
  ex) Reader, Writer <br> 
</details>

-----------------------

### BufferedReader와 BufferedWriter를 사용하는 이유는?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ BufferedReader와 BufferedWriter는 버퍼를 이용해서 입출력 효율을 높일 수 있도록 <br>
  해주는 역할을 합니다. <br>
  버퍼를 이용하면 입출력의 효율이 매우 좋아질 수 있다는 장점이 있습니다.<br> 
  BufferedReader의 readLine()을 사용하면 데이터를 라인 단위로 읽을 수 있습니다. <br> 
</details>

-----------------------

### InputStreamReader와 OutputStreamReader를 사용하는 이유는?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ InputStreamReader와 OutputStreamReader는 바이트 기반 스트림을 문자 스트림으로 연결하는 역할을 합니다. <br>
  그리고 바이트 기반의 스트림의 데이터를 지정된 인코딩의 문자 데이터로 변환합니다. <br> 
</details>

-----------------------

