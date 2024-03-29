# 1주차 Day 3 TIL

#### 2022.08.03

<br/>

## 오늘 한 것 (+ 학습한 것)

### 【1】 Git 공부

- (지금껏 GitHub Desktop 프로그램을 이용해 커밋을 해왔기에, 깃에 대한 자세한 개념을 모르고 명령어에도 익숙치 않음 + PR 경험 X)

- 깃 공부에 도움을 준 <a href="https://backlog.com/git-tutorial/kr/intro/intro1_1.html">사이트 (누구나 쉽게 이용할 수 있는 Git 입문)</a>

<br/>

- <strong>Git 이란</strong>

    - 파일 버전 관리 시스템 (분산형)

    - 파일의 변경사항을 확인, 업데이트 이력을 Git에 모두 저장

<br/>

- <strong>원격 저장소 vs 로컬 저장소</strong>

    - <strong>원격 저장소 (Remote Repository)</strong> : 공용 서버에서 여러 사람과 함께 파일을 관리하는 저장소

    - <strong>로컬 저장소 (Local Repositiory)</strong> : 개인 전용 저장소

    - 로컬 저장소 만드는 방법

        - 완전히 새로운 저장소를 만든다.
        
        - 원격 저장소에서 저장소를 복사해 가져온다.

    - 개인 저장소에서 자신이 작업한 파일을 원격 저장소로 <strong>pull</strong>,  
    원격 저장소에서 다른 사람이 작업한 파일을 개인 저장소로 <strong>push</strong>

<br/>

- <strong>커밋 (commit)</strong>

    - 폴더나 파일의 변경사항을 저장소에 반영하기 위한 작업

    - 좀 더 정확히 말하면, 작업 트리의 변경 사항을 인덱스에 등록하고(스테이징) 이를 저장소에 반영하는 작업

        - 작업 트리(폴더) => 인덱스 => 저장소

<br/>

- <strong>브랜치 (branch)</strong>

    - 독립적으로 작업을 진행하기 위한 버전 개념

    - 각각의 브랜치는 서로의 영향을 받지 않으며, 두 개의 브랜치는 하나로 병합할 수 있다.

    - 모든 작업은 <strong>master 브랜치</strong>에서 시작된다.

    - 통합 브랜치 vs 토픽 브랜치

        - <strong>통합 브랜치 (Integration Branch)</strong>

            - 통합 브랜치는 언제든지 배포할 수 있는 버전을 만들어야 하는 브랜치이다.

            - 모든 기능이 정상적으로 동작하여야 하는 '메인' 브랜치로, 보통 master 브랜치를 통합 브랜치로 사용한다.

        - <strong>토픽 브랜치 (Topic Branch)</strong>

            - 통합 브랜치에서 분기하여 각 기능을 구현하는 작업 단위 브랜치이다.

            - 하나의 토픽 브랜치에서 담당 기능 구현 완료하면 다시 통합 브랜치에 병합한다.

            - 피처 브랜치 (Feature Branch) 라고도 부른다.

<br/>

- <strong>브랜치 전환 (체크아웃 (checkout))</strong>

    - 체크아웃 (checkout) 명령어를 통해 현재 작업 중인 브랜치에서 다른 브랜치로 전환할 수 있다.

    - <strong>stash</strong>

        - 파일의 변경 내용을 일시적으로 저장해두는 곳

        - 브랜치 전환 시 이전의 브랜치에서 작업했던, 아직 커밋하지 않은 내용에 충돌이 발생한 경우

            이 내용을 stash에 잠시 저장해둔 뒤 나중에 원래 혹은 다른 브랜치로 커밋할 수 있다.

<br/>

- <strong>브랜치 통합 (merge, rebase)</strong>

    - merge, rebase 명령어를 통해 여러개의 브런치를 하나로 모을 수 있다.

<br/><br/>

### 【2】 Git Training (PR 연습) (오늘은 반드시 해서 PR을 보내보자)

- 드디어 인생에서 처음으로 PR을 보냈다. (코드숨 git training 레포지토리로)

- 근데 안내대로 따라했을 뿐 아직 그 원리는 잘 모르겠다.

<br/><br/>

## 과제 진행

(오늘도 진행하지 못함)

<br/><br/>

## Feeling

- 모든 과정이 내게 고비다. 하나도 쉽게 할 수 있는 것이 없다.

- 오늘도 코테 대비 캠프로 인해 코드숨 공부를 많이 하지 못했다.

- 게다가 좀 지쳐서 그런지 공부 의욕도 전에 비해 떨어졌다.

- 그래도 오늘을 포함하여 이번 한 주 정말 열심히 살고 있으니 크게 걱정이나 후회는 없다. 

- 진인사대천명 (盡人事待天命)