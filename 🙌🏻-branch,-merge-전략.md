## branch 
 
 - Git-flow 사용
     - hotfix 없는 gitflow
     - feature branch에서 작업 후 develop에 merge
     - 매주 목요일 19:00 전에 main에 merge
     - 하나의 화면단위로 release

- branch 설명
    - feature : 새로운 기능을 개발하는 브랜치 [feature/기능A]
    - develop : 개발한 기능들을 합치는 브랜치 [develop]
    - release : 이번 데모를 준비하는 브랜치 [release/0.1]
    - main : 모든 준비가 완료된 데모를 올리는 브랜치 [main/0.1]

 <img src="https://i.imgur.com/o1xcUmX.png" width=550>

<br/>

 ## merge
 
- fetch & rebase : develop에서 feature로

    ```
    // origin의 develop에서 변경 사항을 가져온다.
    > git switch develop
    > git fetch origin develop
    > git rebase origin/develop
    
    // 작업할 브랜치를 생성한다.
    > git switch -c feature/기능A
    ```
    
- commit & merge : feature에서 develop으로

    ```
    // 현재 작업중인 feature/기능A 브랜치일 때
    // push 전 origin의 develop에서 변경 사항을 가져온다.
    > git fetch origin develop
    > git rebase origin/develop
    
    // conflict가 난다면 해결하고 push한다.
    > git push origin feat/기능A
    ```
    
    <img src=https://i.imgur.com/tRX5KxR.png width=300>
    
- 본인 PR 은 최소 2명에게 리뷰받은 후 본인이 merge 한다.

<br/>

 ## issue/PR/commit 단위

- issue - task
- pr - task
- commit - 자유롭게 (ex. viewController 구현?, bind method 추가..)