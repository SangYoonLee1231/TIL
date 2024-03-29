## Git - 조각 지식 모음

<br/>

- 깃(Git)와 관련된 공부 내용 중 하나의 목차로 분류하기 애매한 지식을 따로 모아 정리하는 곳입니다.

<br/>

### 목차

- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Git/git_piece_info.md#gitignore-%ED%8C%8C%EC%9D%BC"><code>.gitignore</code> 파일</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Git/git_piece_info.md#npm-install-%EC%8B%9C-%EC%A3%BC%EC%9D%98-%EC%82%AC%ED%95%ADs"><code>npm install</code> 시 주의 사항</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Git/git_piece_info.md#git-commit-%EB%A9%94%EC%84%B8%EC%A7%80-%EC%88%98%EC%A0%95%ED%95%98%EA%B8%B0">git commit 메세지 수정하기</a>
<!-- - <a href=""></a> -->

<br/><br/>

## <code>.gitignore</code> 파일

- <code>.gitignore</code>은 Git에서 커밋을 할 때, <strong>무시하고 싶은 파일들의 이름</strong>을 기록하는 파일이다.

  - Git은 기본적으로 디렉토리에서 (숨겨진 파일 포함) 모든 파일을 참조할 수 있다.

  - 따라서 커밋할 때마다 업로드하고 싶지 않은 파일들을 매번 제외해야 하는 귀찮음을 없에기 위해 <code>.gitignore</code> 파일을 만들어 사용한다.

<br/>

- <code>.gitignore</code> 파일 사용 예시

  ```
  .DS_Store
  /node_modules
  /screenshots
  ```

- npm으로 설치한 패키지의 소스 파일(/node_modules)은 용량이 크기 때문에 깃으로 관리하지 않는다.

<br/><br/>

## <code>npm install</code> 시 주의 사항

- 원격 저장소에서 초기 세팅한 파일들을 내 로컬 저장소로 clone 받고, npm install부터 하고나서 branch 생성해야 된다고 한다. (이유는 모르곘지만)

<br/><br/>

## git commit 메세지 수정하기

- `git commit --amend` 명렁어를 통해 수정해주면 된다.

<br/>
