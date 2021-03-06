# 불 논리

<br/>

> 참고 자료 : 개발 도서 『밑바닥부터 만드는 컴퓨터 시스템』 (노암 니산, 시몬 쇼켄 저, 김진홍 옮김 / 인사이트 출판)

<br/>

### 목차

- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/ComputerSystem/computer_system_bool_logic.md#%EB%8F%84%EC%9E%85%EB%B6%80">도입부</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/ComputerSystem/computer_system_bool_logic.md#%EB%B6%88-%EB%85%BC%EB%A6%AC-1">불 논리</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/ComputerSystem/computer_system_bool_logic.md#%EA%B8%B0%EC%B4%88-%EB%85%BC%EB%A6%AC-%EA%B2%8C%EC%9D%B4%ED%8A%B8">기초 논리 게이트</a>

<br/>

## 도입부

- 모든 디지털 기기는 <strong>기초 논리 게이트</strong>로 구성된 칩을 탑재하여, 이를 통해 정보를 저장하고 처리한다.

* 이러한 게이트의 논리적 작동방식은, 물리적 소재 및 제작 기술과 상관 없이 모든 컴퓨터에서 동일하다.

* 불 대수 → 불 함수 → (불) 게이트 순으로 학습하고, 이를 토대로 기초 논리 게이트를 이해한다.

<br/><br/>

## 불 논리

### 불 대수 (Boolean algebra)

- 불 대수는 1과 0을 다루는 대수학이다.

- 더 정확히 말하면, 참/거짓, 1/0, 예/아니오, ON/OFF 같은 2진수 불(bool) 값을 다루는 대수학이다.

- 명제의 참과 거짓을 판단하는 '논리 연산'을 다루며, '불 연산'이라고도 불린다.

<br/>

#### 대표적인 논리 연산 종류

- <code>부정 (Not)</code> : 참과 거짓을 반대로 뒤집는 연산

    <table style="text-align: center">
        <tr><td>a</td><td>out</td></tr>
        <tr><td>0</td><td>1</td></tr>
        <tr><td>1</td><td>0</td></tr>
    </table>

- <code>논리곱 (And)</code> : 두 명제가 모두 참일 때만 결과값이 참인 연산

    <table style="text-align: center">
        <tr><td>a</td><td>b</td><td>out</td></tr>
        <tr><td>0</td><td>0</td><td>0</td></tr>
        <tr><td>0</td><td>1</td><td>0</td></tr>
        <tr><td>1</td><td>0</td><td>0</td></tr>
        <tr><td>1</td><td>1</td><td>1</td></tr>
    </table>

- <code>논리합 (Or)</code> : 두 명제 중 적어도 하나가 참일 때 결과값이 참인 연산

    <table style="text-align: center">
        <tr><td>a</td><td>b</td><td>out</td></tr>
        <tr><td>0</td><td>0</td><td>0</td></tr>
        <tr><td>0</td><td>1</td><td>1</td></tr>
        <tr><td>1</td><td>0</td><td>1</td></tr>
        <tr><td>1</td><td>1</td><td>1</td></tr>
    </table>

- <code>부정 논리곱 (Nand)</code> : 논리곱의 결과값을 부정한 연산

    <table style="text-align: center">
        <tr><td>a</td><td>b</td><td>out</td></tr>
        <tr><td>0</td><td>0</td><td>1</td></tr>
        <tr><td>0</td><td>1</td><td>1</td></tr>
        <tr><td>1</td><td>0</td><td>1</td></tr>
        <tr><td>1</td><td>1</td><td>0</td></tr>
    </table>

- <code>부정 논리합 (Nor)</code> : 논리합의 결과값을 부정한 연산

    <table style="text-align: center">
        <tr><td>a</td><td>b</td><td>out</td></tr>
        <tr><td>0</td><td>0</td><td>1</td></tr>
        <tr><td>0</td><td>1</td><td>0</td></tr>
        <tr><td>1</td><td>0</td><td>0</td></tr>
        <tr><td>1</td><td>1</td><td>0</td></tr>
    </table>

- <code>배타적 논리합 (Xor)</code> : 두 명제의 참거짓 여부가 반대여야만 결과값이 참인 연산

    <table style="text-align: center">
        <tr><td>a</td><td>b</td><td>out</td></tr>
        <tr><td>0</td><td>0</td><td>0</td></tr>
        <tr><td>0</td><td>1</td><td>1</td></tr>
        <tr><td>1</td><td>0</td><td>1</td></tr>
        <tr><td>1</td><td>1</td><td>0</td></tr>
    </table>

<br/>

### 불 함수 (Boolean Function)

- 불 함수는 2진수를 입력받아 2진수로 출력하는 함수이다.

- 컴퓨터는 2진수로 모든 작업을 처리하는 하드웨어이므로, 불 함수는 하드웨어 아키텍처(의 명세, 구성, 최적화)에 중심적인 역할을 한다.

<br/>

#### 불 함수를 표현하는 여러가지 방식

- <strong>진리표 표현</strong>

  - 불 함수의 입력값과 출력값(결과값)을 나란히 서술하여 표현하는 방법이다. 위에서 다양한 논리 연산을 소개할 때 이러한 진리표를 이용하였다.

    <table style="text-align: center">
        <tr><td>a</td><td>b</td><td>out</td></tr>
        <tr><td>0</td><td>0</td><td>1</td></tr>
        <tr><td>0</td><td>1</td><td>1</td></tr>
        <tr><td>1</td><td>0</td><td>1</td></tr>
        <tr><td>1</td><td>1</td><td>0</td></tr>
    </table>

- <strong>정준 표현</strong>

  - 함수의 진리표에서 함수값이 1인 행들을 And 연산으로 묶어 항으로 만들고 이를 Or 연산으로 이어주면, 진리표와 동등한 불 표현식을 얻을 수 있다.

    <table style="text-align: center">
        <tr><td>x</td><td>y</td><td>z</td><td>out</td></tr>
        <tr><td>0</td><td>0</td><td>0</td><td>0</td></tr>
        <tr><td>0</td><td>0</td><td>1</td><td>0</td></tr>
        <tr><td>0</td><td>1</td><td>0</td><td>1</td></tr>
        <tr><td>0</td><td>1</td><td>1</td><td>0</td></tr>
        <tr><td>1</td><td>0</td><td>0</td><td>1</td></tr>
        <tr><td>1</td><td>0</td><td>1</td><td>0</td></tr>
        <tr><td>1</td><td>1</td><td>0</td><td>1</td></tr>
        <tr><td>1</td><td>1</td><td>1</td><td>0</td></tr>
    </table>

    <code>f(x, y, z) = x'yz' + xy'z' + xyz'</code> (바(-) 대신 '로 표기)

    <br/>

#### Nand 함수의 중요한 성질

- Nand 함수만으로 And, Or, Not 연산을 모두 만들 수 있다.

- 모든 불 함수는 And, Or, Not 연산으로만 이루어진 정준 표현식으로 나타낼 수 있다.

- ✨ 즉, 모든 불 함수는 Nand 함수만으로 표현할 수 있다.

<br/>

### 게이트 (또는 칩)

- 게이트는 불 함수를 물리적으로 구현한 장치이다.

- 게이트의 입력 핀에 어떤 값 v1, v2, ... 이 들어가면, 게이트의 '논리'(내부 구조)가 출력값을 계산하여, 출력 핀으로 값 f(v1...vn)을 내보낸다.

- 모든 논리 게이트는 입력과 출력의 신호 형태가 동일하므로, 게이트를 연달아 이으면 더 복잡한 기능을 수행하는 조합 게이트를 만들 수 있다.

- 게이트 내부의 회로, 스위치, 릴레이, 전원 공급장치 같은 물리적인 영역은 컴퓨터 과학자들이 신경 쓰지 않아도 된다.

<br/><br/>

## 기초 논리 게이트

- 모든 논리 게이트는 Nand 게이트로 구현할 수 있다.

- 즉, Nand 게이트가 컴퓨터 아키텍처의 시작점인 것이다.
