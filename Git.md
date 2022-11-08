# Git
<br>

-----------------------

### Git 스냅샷이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 스냅샷이란 마치 사진을 찍듯이, 특정 시점에 스토리지의 파일 시스템을 포착해 보관하는 기술을 의미합니다. <br>
  Git은 데이터를 파일들의 집합으로 관리하지 않고, 스냅샷의 연속으로 관리합니다. <br>
  즉, Git은 데이터를 스냅샷의 스트림으로 취급합니다. <br> 
</details>

-----------------------

### Git의 무결성이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Git은 데이터를 저장하기 전에 항상 체크섬을 구하고, 그 체크섬으로 데이터를 관리합니다. <br>
  Git은 SHA-1 해시를 통해 체크섬을 만드는데, 체크섬은 40글자 길이의 16진수 문자열입니다. 
  
</details>

-----------------------

### Git은 파일을 3가지 상태로 관리하는데 각각은 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Git은 파일을 Committed, Modified, Staged 이렇게 3가지 상태로 관리합니다. <br> 
  Committed란 데이터가 로컬 데이터베이스에 안전하게 저장되었음을 의미합니다. <br> 
  Modified란 수정한 데이터를 아직 로컬 데이터베이스에 커밋하지 않은 것을 의미합니다. <br>  
  Staged란 현재 수정한 파일을 곧 커밋할 것이라고 표시한 상태를 의미합니다. <br>  
  
</details>

-----------------------

### git init 명령을 실행하면 어떤 일이 발생하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ .git 이라는 하위 디렉토리가 만들어집니다. 
   이 때, .git 디렉토리에는 저장소에 필요한 뼈대(skeleton) 파일들이 들어 있습니다. 
 
</details>

-----------------------

### .git 디렉토리란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 
 
</details>

-----------------------

### git 브랜치란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ git 브랜치란 커밋 사이를 가볍게 이동할 수 있는 어떤 포인터 같은 것입니다. 
 
</details>

-----------------------

### Git에서 HEAD라는 특수한 포인터의 역할은 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ HEAD는 현재 작업중인 로컬 브랜치를 가리킵니다.  
 
</details>

-----------------------

### git checkout 명령이란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Git에서 다른 브랜치로 이동할 수 있는 명령을 의미합니다.  
 
</details>

-----------------------
