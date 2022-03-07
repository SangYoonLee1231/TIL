# JavaScript 기본 3 - 기본 연산자

> 참고 자료 : <a href="https://ko.javascript.info/">javascript.info</a>

<br/>

- <a href="https://ko.javascript.info/">javascript.info</a>의 【자바스크립트 기본】 챕터 8장 내용

<br/>

### 목차

- <a href="">연산자 관련 용어</a>
- <a href="">산술 연산자</a>
- <a href="">'+' 연산자의 기능</a>
- <a href="">연산자 우선순위</a>
- <a href="">할당 연산자</a>
- <a href="">증가/감소 연산자</a>
- <a href="">비트 연산자</a>
- <a href="">쉼표 연산자</a>
- <a href=""></a>
- <a href=""></a>

<br/><br/>

## 연산자 관련 용어

- 피연산자

  - 연산자가 연산을 수행하는 대상

  - '인수(Agrument)'라고도 부른다.

  - 피연산자의 개수가 1개인지 2개인지에 따라 연산자의 종류가 '단항 연산자' 혹은 '이항 연산자'로 나뉜다.

<br/>

- 단항 (Unary) 연산자

  - 피연산자를 하나만 받아 계산하는 연산자

  - 대표젹인 예로 피연산자의 부호를 뒤집는 딘항 마이너스 연산자 <code>-</code>가 있다.

<br/>

- 이항 (Binary) 연산자

  - 피연산자가 두 개 필요한 연산자

  - <code>5 - 3</code>처럼 뺄셈 연산을 하는 이항 마이너스 연산자 <code>-</code>가 그 예다.

<br/>

- 같은 모양의 연산자라 하더라도 단항 연산자인가 이항 연산자인가에 따라 수행하는 연산 및 연산자 우선순위가 달라진다.

<br/>

## 산술 연산자

- 덧셈 연산자 <code>+</code>

- 뻴셈 연산자 <code>-</code>

- 곱셈 연산자 <code>\*</code>

- 나눗셈 연산자 <code>/</code>

  - 표현식 <code>a % b</code>는 a를 b로 나눈 몫을 반환합니다. 몫이 정수면 정수로, 실수면 실수로 반환합니다.

- 나머지 연산자 <code>%</code>

  - 표현식 <code>a % b</code>는 a를 b로 나눈 후 그 나머지를 정수로 반환합니다.

- 거듭제곱 연산자 <code>a \*\* b</code>

  - 표현식 <code>a \*\* b</code>는 a를 b번 곱한, 즉 a의 b제곱 값을 반환합니다.

  - 이 때 b의 값은 정수가 아닌 숫자에 대해서도 동작한다. b에 <code>1/2</code>을 넣으면 제곱근을 구할 수 있다.

    ```javascript
    alert(4 ** (1 / 2)); // 2
    ```

<br/><br/>

## ✨ '+' 연산자의 기능

### 단항 연산자 '+'

- 숫자에 단항 연산자 '+'을 붙이면 아무런 일이 일어나지 않는다.

- 그러나 숫자가 아닌 값이 '+'을 붙이면, 그 피연산자는 <strong>숫자형으로 형변환</strong>이 일어난다.

- 즉, 단항 연산자 '+'은 <code>Number(...)</code>와 동일한 일을 수행하는 것이다.

  ```javascript
  let num1 = -2;
  let num2 = "10";

  alert(+num1); // -2
  alert(+num2); // 10

  alert(+""); // 0
  alert(+undefined); // NaN
  ```

- HTML 폼(form) 필드에서 숫자로 된 문자열 값(예: <code>"2"</code>)을 가져올 때, 단항 연산자를 사용해 숫자로 형변환을 해줄 수 있다.

<br/>

### 이항 연산자 '+'

- 이항 연산자 '+'은 피연산자 2개를 더한 값을 반환한다.

  ```javascript
  alert(3 + 4); // 7
  ```

<br/>

- 그런데 만약 피연산자 2개에 문자열이 전달되면, 덧셈 연산자는 덧셈을 하지 않고 두 문자열을 병합힌다.

  ```javascript
  alert("3" + "4"); // "34"
  ```

<br/>

- 만일 피연산자 2개 중 하나만 문자열이라면, 덧셈 연산자는 <strong>나머지 하나를 문자열로 형변환하고 서로 병합</strong>한다.

  ```javascript
  alert("3" + 4); // "34"

  alert(2 + 3 + "4"); // "54"
  ```

  - 연산은 왼쪽에서 오른쪽으로 진행되므로, <code>2 + 3 + "4"</code>에서 숫자 2와 3이 먼저 더해지고, 그 값 5가 문자열 4와 병합되어 "54"가 되는 것이다.

<br/>

- 반대로 <strong>덧셈 이외의 산술 연산자</strong>는 피연산자가 숫자가 아닌 경우, <strong>그 형을 숫자형으로 변환</strong>한다. (오직 숫자형만 다루는 연산자들이다)

  ```javascript
  alert("-9" - 5); // -14
  alert(2 * "3"); // 6
  alert("6" / "2"); // 3
  ```

<br/><br/>

## 연산자 우선순위

- 하나의 표현식에 둘 이상의 연산자가 있는 경우, 실행 순서는 연산자 우선순위에 의해 결정된다.

- 우선순위가 클수록 먼저 실행된다. 우선순위가 동일하면 왼쪽에서 오른쪽 순으로 실행된다.

- 연산자 우선순위는 기억할 필요 없다. 먼저 계산하고 싶은 연산을 <strong>괄호</strong>로 묶으면 된다.

- 단항 연산자는 이항 연산자보다 높은 우선순위를 갖는다.

  - 단항 덧셈 연산자가 이항 덧셈 연산자보다 먼저 실행되므로, 표현식 <code>" +'1' + +'2' "</code>에선 형변환이 먼저 일어나 <code>3</code>의 값이 된다.

<br/><br/>

## 할당 연산자

### 할당 연산자의 값 반환

### 할당 연산자 체이닝

-

<br/><br/>

## 증가/감소 연산자

<br/><br/>

## 비트 연산자

<br/><br/>

## 쉼표 연산자