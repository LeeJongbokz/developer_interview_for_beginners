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

### Git에서 워킹 디렉토리의 모든 파일은 크게 어떻게 나뉘는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Tracked(관리대상임) 와 Untracked(관리대상이 아님) 으로 나뉩니다. 
 
</details>

-----------------------

### Git에서 Tracked 파일은 어떤 파일이고, 어떻게 분류되는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Tracked 파일은 이미 스냅샷에 포함돼 있던 파일이고, <br> 
  Tracked 파일은 Unmodified(수정하지 않음), Modified(수정함), Staged(커밋으로 저장소에 기록할)로 구분됩니다. 
 
</details>

-----------------------

### git clone 명령은 어떤 기능을 하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 저장소를 clone 하는 기능을 한다. <br> 
 
</details>

-----------------------

### 마지막 커밋 이후 아직 아무것도 수정하지 않은 상태에서 어떤 파일을 수정하면 Git은 그 파일을 어떤 상태로 인식하는가?
### 그리고 이 파일을 실제로 커밋하기 위해서는 어떤 상태로 만들어야 하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Modified 상태로 인식합니다. <br>
  Staged 상태로 만들어야 합니다. <br>
 
</details>

-----------------------

### 파일의 상태를 확인하려면 보통 어떤 명령을 사용해야 하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ git status 명령을 사용해야 합니다. <br>
 
</details>

-----------------------

### Git은 Untracked 파일은 아직 어디에 넣어지지 않은 파일이라고 보는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 스냅샷(커밋)에 넣어지지 않은 파일이라고 본다. <br>
 
</details>

-----------------------

### Git add 명령으로 무엇을 할 수 있는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 파일을 새로 추적할 수 있다. <br>
 
</details>

-----------------------

### Changes To be committed에 들어 있는 파일은 어떤 상태라는 것을 의미하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Staged 상태라는 것을 의미한다. <br>
 
</details>

-----------------------

### Staged 상태로 만들려면 어떤 명령을 실행해야 하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ git add 명령을 실행해야 한다. <br>
 
</details>

-----------------------

### git add 명령을 실행한 후에 또 파일을 수정하면 무엇을 해야 하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ git add 명령을 다시 실행해서 최신 버전을 Staged 상태로 만들어야 한다. <br>
 
</details>

-----------------------


### git add 명령을 실행한 후에 또 파일을 수정하면 무엇을 해야 하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ git add 명령을 다시 실행해서 최신 버전을 Staged 상태로 만들어야 한다. <br>
 
</details>

-----------------------

### Git이 관리할 필요가 없는 파일은 어떻게 하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ .gitignore 파일을 만들고, 그 안에 무시할 파일 패턴을 적습니다. <br>
 
</details>

-----------------------

### 단순히 파일이 변경되었다는 것이 아니라 어떤 내용이 변경됐는지 살펴보려면 어떻게 하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ git status 명령이 아니라 git diff 명령을 사용해야 합니다.  <br>
 
</details>

-----------------------

### 만약 커밋하려고 Staging Area에 넣은 파일의 변경 부분을 보고 싶으면, 어떤 옵션을 사용하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ git diff --staged 옵션을 사용한다.  <br>
 
</details>

-----------------------

### 변경 사항을 커밋하는 명령어는 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ git commit이다.  <br>
 
</details>

-----------------------

### Git에서 파일을 제거하려면 어떻게 하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ git rm 명령으로 Tracked 상태의 커밋을 삭제한 후 커밋해야 한다.  <br>
 
</details>

-----------------------

### git mv 명령이란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 파일의 이름을 변경하는 명령어이다.   <br>
 
</details>

-----------------------

### git에서 커밋 히스토리를 조회하는 명령어는 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ git log이다.   <br>
 
</details>

-----------------------
