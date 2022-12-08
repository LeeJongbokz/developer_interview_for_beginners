# Git 브랜치
<br>


-----------------------

### 버전 관리란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 버전 관리 시스템은 파일 변화를 시간에 따라 기록했다가 <br> 
  나중에 특정 시점의 버전을 다시 꺼내올 수 있는 시스템입니다. 
</details>


-----------------------

### 모든 버전 관리 시스템은 무엇을 지원하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 브랜치를 지원한다. 개발을 하다 보면 코드를 여러 개로 복사해야 하는 일이 자주 생깁니다. <br> 
  코드를 통째로 복사하고 나서 원래 코드와는 상관없이 독립적으로 개발을 진행할 수 있는데, <br>
  이렇게 독립적으로 개발하는 것이 브랜치입니다. <br> 
  
  다른 버전 관리 시스템과는 달리 Git은 브랜치를 만들어 작업하고 나중에 Merge하는 방법을 권장합니다. <br> 
  심지어 하루에 수십 번씩 해도 괜찮습니다. 
</details>


-----------------------

### 커밋하면 Git은 무엇을 저장하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 현 Staging Area에 있는 데이터의 스냅샷에 대한 포인터, <br>
  저자나 커밋 메시지 같은 메타데이터, <br> 
  이전 커밋에 대한 포인터 등을 포함하는 커밋 개체를 저장합니다. 
</details>

-----------------------

### Git commit으로 커밋하면 무슨 일이 발생하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 먼저 루트 디렉터리와 각 하위 디렉터리의 트리 개체를 <br> 
  체크섬과 함께 저장소에 저장합니다. 
</details>

-----------------------

### Git의 브랜치란 무엇입니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 커밋 사이를 가볍게 이동할 수 있는 어떤 포인터 같은 것입니다. <br> 
  기본적으로 Git은 master 브랜치를 만듭니다. <br> 
  처음 커밋하면 이 master 브랜치가 생성된 커밋을 가리킵니다. <br>
  이후 커밋을 만들면 브랜치는 자동으로 가장 마지막 커밋을 가리킵니다. 
</details>

-----------------------

### 지금 작업 중인 브랜치가 무엇인지 Git은 어떻게 파악하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 다른 버전 관리 시스템과는 달리 Git은 'HEAD'라는 특수한 포인터가 있습니다. <br> 
  이 포인터는 지금 작업하는 로컬 브랜치를 가리킵니다. <br> 
  
</details>

-----------------------

### 어떤 명령으로 다른 브랜치로 이동할 수 있습니까?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ git checkout 명령으로 다른 브랜치로 이동할 수 있습니다. <br> 
  
</details>

-----------------------

### 중요한 문제가 생겨서 그것을 해결하는 Hotfix를 만들 때는 어떤 절차에 의해서 발생하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 1. 새로운 이슈를 처리하기 이전의 운영(Production) 브랜치로 이동합니다. <br>
  2. Hotfix 브랜치를 새로 하나 생성합니다. <br> 
  3. 수정한 Hotfix 테스트를 마치고 운영 브랜치로 Merge합니다. <br>
  4. 다시 작업하던 브랜치로 옮겨가서 하던 일을 진행합니다. <br> 
  
</details>

-----------------------

### Git은 Merge하지 못하면 어떤 메시지를 출력하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Git은 Merge 하지 못하면 충돌(Conflict) 메시지를 출력합니다. <br>
  Git이 자동으로 Merge하지 못하면 새 커밋이 생기지 않습니다. <br>
  변경사항의 충돌을 개발자가 해결하지 않는 한 Merge 과정을 진행할 수 없습니다. <br>
  Merge 충돌이 일어났을 때 Git이 어떤 파일을 Merge할 수 없었는지 살펴보려면 <br>
  git status 명령을 이용합니다. <br>
  충돌이 일어난 파일은 unmerged 상태로 표시됩니다. <br> 
  
</details>

-----------------------

### 리모트 Refs란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 리모트 저장소에 있는 포인터인 레퍼런스입니다. <br> 
  리모트 저장소에 있는 브랜치, 태그 등등을 의미합니다. 
  
</details>

-----------------------

### Push하기란 무엇인가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 로컬의 브랜치를 서버로 전송하려면 쓰기 권한이 있는 리모트 저장소에 Push해야 합니다. <br>
  로컬 저장소의 브랜치는 자동으로 리모트 저장소로 전송되지 않습니다. <br> 
  명시적으로 브랜치를 push해야 정보가 전송됩니다. 
  
</details>

-----------------------


### Fast-forward란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Merge 방식의 일종으로, Merge할 브랜치가 현 브랜치 커밋의 Upstream 브랜치이기 때문에, <br>
  master 브랜치 포인터는 Merge 과정 없이 그저 최신 커밋으로 이동하는 것을 의미합니다. <br> 
</details>

-----------------------

### 3-way merge란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ 현재 브랜치가 가리키는 커밋이 Merge할 브랜치의 조상이 아닌 경우, <br>
  Git이 각 브랜치가 가리키는 커밋 두 개와 공통 조상 하나를 사용하여 하는 Merge 방식을 의미합니다. <br> 
  
</details>

-----------------------

### 어떤 경우에 3-way merge가 실패하는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Merge하는 두 브랜치에서 같은 파일의 한 부분을 동시에 수정하고 Merge하면, <br>
  Git은 해당 부분을 Merge하지 못합니다. <br> 
  
</details>

-----------------------
