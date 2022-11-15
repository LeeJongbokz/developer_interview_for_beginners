# Git 브랜치
<br>

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
