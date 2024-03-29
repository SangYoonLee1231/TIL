# 파일 I/O Part 3 (File Offset)

<br/>

> 참고 자료 : '시스템 프로그래밍' 학부 수업 자료

<br/><br/>

### 목차

- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Operating_System/System_Programming_Linux/file_offset.md#file-offset%EC%9D%B4%EB%9E%80">File Offset이란?</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Operating_System/System_Programming_Linux/file_offset.md#%ED%8C%8C%EC%9D%BC%EC%9D%84-%EB%8B%A4%EB%A3%A8%EB%8A%94-%EB%B0%A9%EB%B2%95">파일을 다루는 방법</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Operating_System/System_Programming_Linux/file_offset.md#file-offset-%EA%B4%80%EB%A0%A8-%ED%95%A8%EC%88%98">File Offset 관련 함수</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Operating_System/System_Programming_Linux/file_offset.md#%EC%B6%94%EA%B0%80%EC%A0%81%EC%9C%BC%EB%A1%9C-%EC%A7%9A%EA%B3%A0-%EB%84%98%EC%96%B4%EA%B0%88-%ED%95%A8%EC%88%98">추가적으로 짚고 넘어갈 함수 (`sprintf`, `sscanf`, `ferror`, `feof`, `clearerr`)</a>
<!-- - <a href=""></a> -->

<br/><br/>

### File Offset이란?

- 보통 파일을 오픈하고 read를 하면 맨 처음부터(위에서부터) 읽고, 중간에 쉬었다가 다시 읽으면 그 다음 부분부터 읽는다.

- 즉, 어딘가에 현재 읽어야 할 위치 정보를 저장하고 있어야 한다.

- File Offest은 이 위치를 가리키는 포인터를 말한다.

- 파일을 처음에 열면, File Offset은 시작 위치를 자동으로 가리키고, 파일을 읽으면 읽은만큼 전진한다. (항상 다음 읽어야 할 위치를 가리킴)

- appending 모드(파일 뒤에 내용을 덧붙이는 모드)로 파일을 열면 File Offset은 맨 끝 위치를 가리킨다. → write하면 그 위치에 데이터를 쓴다.

<br/><br/>

### 파일을 다루는 방법

#### Sequential Access

- 파일을 순차적으로 읽고 쓰는 작업

#### Random Access

- 경우에 따라 파일을 여기 저기 왔다갔다 하면서 작업을 해야 할 때가 있다 (임의의 위치)

- 데이터를 원하는 위치에 쓰려면 원하는 위치로 Offset을 우선 옮겨야 한다.

  → `fseek`(라이브러리 함수), `lseek` (시스템 콜 함수)

- 데이터를 관리하는 기본 단위인 레코드(record) 단위로 이동한다.

<br/><br/>

### File Offset 관련 함수

#### `int fseek (FILE *stream, long offset, int sopt)`

- 라이브러리 함수

- `FILE *stream` : 대상 파일의 스트림

- `offset` : 어디로 옮길지의 값

  - SEEK_SET : 시작 위치로부터 offset 바이트만큼 떨어진 곳으로 offset을 옮긴다.

  - SEEK_CUR : 현재 offset 위치로부터 상대적으로 offset만큼 옮겨라 (음수가 되면 파일 앞쪽으로 이동)

  - SEEK_END : 파일 끝이 기준, 맨 끝에서부터 상대적으로 offset만큼 옮겨라

- return 값 → 정상 : 0, 비정상 : -1

<br/>

#### `off_t lseek(int fd, off_t offset, int whence);`

- 시스템 콜 함수

- fseek 기능과 거의 동일

- fd : 파일 디스크립터 번호

- return 값 → 정상 : 파일의 시작점부터 현재 위치까지의 거리, 비정상 : -1

- 파일의 크기 구하는 방법 : SEEK_END 설정 후 return 값을 확인

<br/>

#### `void rewind (FILE *stream)`

- Offset을 맨 앞으로 옮겨라

<br/>

#### `long ftell (FILE *stream)`

- 현재 Offset의 값을 물어보는 함수

- 비정상적으로 동작하면 return 값은 -1이 된다.

<br/><br/>

### 추가적으로 짚고 넘어갈 함수

- `sprintf` : 출력의 결과를 캐릭터 버퍼에 출력 (화면에 바로 안나옴)

  - `s`는 string을 의미

  - return 값 → 정상 : input 길이, 비정상 : EOF

- `sscanf` : 어떤 버퍼에 뭔가 문자열이 들어있을 때 거기에서 값을 가져오라

  - return 값 → 정상 : input 길이, 비정상 : EOF

- `ferror` : 어떤 파일 스트림을 조작하는 과정 중에 에러가 발생했는지를 확인하는 명령

  - 없으면 0, 발생했으면 0이 아님

- `feof` : End Of File에 도착했는가?

  - 정상적으로 읽으면 0 리턴, 파일 끝에서 EOF을 넘어서 뭔가 시도하려고 하면 0 아닌 값 리턴

  - 파일 끝에 도달했는가?

    - True → 0이 아닌 값, False → 0

  - feof는 파일 스트림으로 열어야 한다.

- `clearerr` : 에러를 무시해도 되는 상황에서 해당 에러를 지우고 새로 시작하자

<br/>
