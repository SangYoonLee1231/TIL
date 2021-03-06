# 컴퓨터 구조의 큰 개요

<br/>

> 참고 자료 : 개발 도서 『밑바닥부터 만드는 컴퓨터 시스템』 (노암 니산, 시몬 쇼켄 저, 김진홍 옮김 / 인사이트 출판)

<br/>

## 컴퓨터 시스템 추상화 계층

[소프트웨어 계층]

- 인간 사고

  &nbsp; ↓ &nbsp; 응용프로그램 혹은 시스템 설계

- 고수준 언어 & 운영체제

  &nbsp; ↓ &nbsp; 컴파일러

- 가상 머신

  &nbsp; ↓ &nbsp; VM 번역기

- 어셈블리 언어

  &nbsp; ↓ &nbsp; 어셈블러

[하드웨어 계층]

- 기계어

  &nbsp; ↓ &nbsp; 컴퓨터 아키텍처

- 하드웨어 플랫폼

  &nbsp; ↓ &nbsp; 게이트 논리

- 칩과 논리 게이트

  &nbsp; ↓ &nbsp; 전기공학

- 물리학

<br/><br/>

## 고수준 언어를 컴퓨터가 해석하는 과정

- 고수준 언어로 작성된 텍스트를 컴퓨터가 이해하기 위해 내부에서 어떤 일이 일어나야 하는지 단순하고 간략하게 살펴보자.

<br/>

- 우선, 고수준 언어로 작성된 텍스트를 분석해서 그 의미를 파악해야 한다. 이를 위해선, 호스트 <strong>운영체제</strong>나 <strong>표준 라이브러리</strong>의 역할이 중요하다.

- 텍스트의 의미를 파악한 후, 고수준 언어는 <strong>컴파일</strong>아란 번역 과정을 통해 저수준 언어인 <strong>기계어</strong>로 다시 표현된다.

- 컴파일 과정은 보통 <strong>컴파일러</strong>, <strong>가상 머신 구현</strong>, <strong>어셈블러</strong>라는 세 가지 번역 과정으로 나뉜다.

- 이렇게 번역된 기계어도 아직 (2진 코드로) 추상화된 개념이다. 따라서 기계어를 이제 실현해주는 과정이 진행되어야 한다. 이 때 필요한 것이 <strong>하드웨어 아키텍처</strong>이다.

- <strong>하드웨어 아키텍처</strong>는 레지스터, 메모리 장치, ALU 같은 칩들로 구현된다.

- 이런 하드웨어들은 모두 <strong>기초 논리 게이트</strong>로 만들어진다.

- 그리고, <strong>기초 논리 게이트</strong>는 Nand나 Nor같은 <strong>기본 게이트</strong>로 구성된다.

- 다시 논리 게이트는 트랜지스터로 구성되는데 이 이하는 물리학의 영역이라 신경쓰지 않아도 된다.

<br/><br/>

## 다루는 주제

### 하드웨어

- 논리 게이트
- 불 산술
- 멀티플렉서
- 플립플롭
- 레지스터
- 램 (RAM) 유닛
- 카운터
- 하드웨어 기술 언어
- 칩 시뮬레이션 및 테스트

### 아키텍처

- ALU/CPU 설계 및 구현
- 기계 코드, 어셈블리 언어 프로그래밍
- 주소 지정 방법
- 메모리 매핑 입력/출력

### 운영체제

- 메모리 관리
- 수학 라이브러리
- 기본 I/O 드라이버
- 스크린 관리
- 파일 I/O
- 고수준 언어 지원

### 프로그래밍 언어

- 객체 기반 설계 및 프로그래밍
- 추상 데이터 유형
- 범위 지정 규칙
- 구문 및 의미
- 참조

### 컴파일러

- 어휘 분석
- 하양식 파싱
- 기호 테이블
- 가상 스택 기반 머신
- 코드 생성
- 배열 및 객체 구현

### 데이터 구조 및 알고리즘

- 스택
- 해시 테이블
- 리스트
- 재귀 알고리즘
- 산술 알고리즘
- 기하학적 알고리즘
- 실행시간 고려

### 소프트웨어 공학

- 모듈식 설계
- 인터페이스/구현 패러다임
- API 설계 및 문서화
- 사전 테스트 계획
- 대규모 프로그래밍
- 품질 보증

<br/><br/>

##
