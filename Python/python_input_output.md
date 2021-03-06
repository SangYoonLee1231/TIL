# Python - 입력 함수 <code>input()</code> 사용법

<br/>

> 참고 자료 : <a href="https://www.codetree.ai/missions/4">Code Tree - Novice Low</a>

<br/>

### 목차

- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Python/python_input_output.md#%EA%B8%B0%EB%B3%B8-%EC%9E%85%EB%A0%A5-%EB%B0%A9%EB%B2%95">기본 입력 방법</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Python/python_input_output.md#%EB%AC%B8%EC%9E%90%EC%97%B4%EC%9D%84-%EB%82%98%EB%88%A0%EC%84%9C-%EC%9E%85%EB%A0%A5-%EB%B0%9B%EA%B8%B0">문자열을 나눠서 입력 받기</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Python/python_input_output.md#1%EC%B0%A8%EC%9B%90-%EB%A6%AC%EC%8A%A4%ED%8A%B8-%EC%9E%85%EB%A0%A5-inputsplit-%ED%99%9C%EC%9A%A9%EB%B2%95">1차원 리스트 입력 (<code>input().split()</code> 활용법)</a>

<br/><br/>

## 기본 입력 방법

- python에선 <code>input()</code>함수를 통해 한 줄 단위로 문자열을 입력 받을 수 있다.

  ```python
  a = input()

  print(f"a = {a}")
  ```

  ▼ 입력 및 출력 결과

  ```
  >> Hello World

  a = Hello World
  ```

  ```
  >> 4

  a = 4    (이때 4는 문자열 "4"이다.)
  ```

<br/>

### 문자열이 아닌 다른 자료형으로 입력 받기

- <code>input()</code>함수로 입력받을 때, 입력값의 자료형이 정수나 실수여도 문자열로 인식된다.

  ```python
  b = input()

  print(b + 1)
  ```

  ▼ 입력 및 출력 결과

  ```
  >> 4

  ----> 4 print(b + 1)

  TypeError: can only concatenate str (not "int") to str
  ```

<br/>

- 문자열에 숫자를 더할 순 없으므로 에러가 발생하는 것이다.

- 숫자로만 이루어진 문자열을 다른 자료형으로 바꾸기 위해선, 아래와 같이 형변환을 해주어야 한다.

  ```python
  b = int(input())

  print(b + 1)
  ```

  ▼ 입력 및 출력 결과

  ```
  >> 4

  5
  ```

<br/>

- 또는 아래와 같이 값을 우선 입력 받고 형변환을 해줘도 된다.

  ```python
  b = input()
  b = int(b)

  print(b + 1)
  ```

  ▼ 입력 및 출력 결과

  ```
  >> 4

  5
  ```

<br/>

- 실수형이라면 <code>float()</code>로 감싸주면 된다.

  ```python
  c = float(input())

  print(c + 0.32)
  ```

  ▼ 입력 및 출력 결과

  ```
  >> 2.23

  2.55
  ```

<br/><br/>

## 문자열을 나눠서 입력 받기

- python에서 <code>split()</code>함수는 특정 기준으로 문자열을 자르는 함수이다.

<br/>

- <code>split()</code>함수를 그대로 사용하면, 공백을 기준으로 문자열을 자르고, 잘려나간 각 요소를 원소로 갖는 하나의 리스트가 만들어진다.

  ```python
  a = input()
  print(a.split())
  ```

  ▼ 입력 및 출력 결과

  ```
  >> Hello World
  ['Hello', 'World']
  ```

<br/>

- <code>split()</code>함수 안에 다른 문자를 넣으면, 공백 대신 그 문자를 기준으로 문자열을 자른다.

  ```python
  a = input()
  print(a.split("."))
  ```

  ▼ 입력 및 출력 결과

  ```
  >> 20.48.67
  ['20', '48', '67']
  ```

<br/>

- ✨ <code>input()</code>함수와 <code>split()</code>함수를 같이 이어 쓰면, 입력 받은 문자열을 나눠서 리스트로 바로 저장할 수 있다.

  ```python
  arr = input().split()
  n = int(arr[0])
  m - int(arr[1])

  print(n, m, n * m, sep="\n")
  ```

  ▼ 입력 및 출력 결과

  ```
  >> 16 12

  16
  12
  192
  ```

<br/><br/>

## 1차원 리스트 입력 (<code>input().split()</code> 활용법)

- <code>input().split()</code>으로 공백을 사이에 두고 주어지는 입력값을 나눠 받을 수 있다.

  ```python
  arr = input().split()

  print(arr)
  ```

  ▼ 입력 및 출력 결과

  ```
  >> 1 3 5

  ['1', '3', '5']
  ```

<br/>

- 여기서 <code>map</code>을 활용하면, 입력받는 모든 값에 원하는 함수를 적용시킬 수 있다.

  ```python
  arr = list(map(int, input().split()))

  print(arr)
  ```

  ▼ 입력 및 출력 결과

  ```
  >> 1 3 5

  [1, 3, 5]
  ```

<br/>

- 이 때, 입력받을 값의 개수가 고정되어 있으면, <code>list()</code>함수 대신 <code>tuple()</code>함수를 쓰는 것이 좋다. (unpacking 활용)

  ```python
  n, m = tuple(map(int, input().split()))

  print(n, m)
  ```

  ▼ 입력 및 출력 결과

  ```
  >> 1 3

  1 3
  ```
