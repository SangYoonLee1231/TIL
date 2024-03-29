## Python - 조각 지식 모음

<br/>

- 파이썬과 관련된 공부 내용 중 하나의 목차로 분류하기 애매한 지식을 따로 모아 정리하는 곳입니다.

<br/>

### 목차

- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Python/python_piece_info.md#%ED%8C%8C%EC%9D%B4%EC%8D%AC%EC%97%90%EC%84%9C-%EB%B3%80%EC%88%98%EC%9D%98-scope-%EB%B2%94%EC%9C%84">파이썬에서 변수의 scope 범위</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Python/python_piece_info.md#2%EC%B0%A8%EC%9B%90-%EB%B0%B0%EC%97%B4-%EC%84%A0%EC%96%B8-%EC%8B%9C-%EC%9C%A0%EC%9D%98-%EC%82%AC%ED%95%AD">2차원 배열 선언 시 유의 사항</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Python/python_piece_info.md#python%EC%9D%98-%EC%B5%9C%EB%8C%80-%EC%A0%95%EC%88%98%EA%B0%92-sysmaxsize-%ED%99%9C%EC%9A%A9%ED%95%98%EA%B8%B0">python의 최대 정수값 <code>sys.maxsize</code> 활용하기</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Python/python_piece_info.md#typeerror-sequence-item-0-expected-str-instance-int-found-%ED%95%B4%EA%B2%B0-int%ED%98%95-list-join%ED%95%98%EA%B8%B0">TypeError: sequence item 0: expected str instance, int found 해결 (int형 list join하기)</a>
<!-- - <a href=""></a>
- <a href=""></a> -->

<br/>

## 파이썬에서 변수의 scope 범위

- 파이썬에서 <code>for</code>문이나 <code>if</code>문, 또는 함수의 내부에 선언한 지역 변수는 놀랍개도 main 함수 영역(indent가 없는 코드 영역)에서도 그대로 사용할 수 있다.

  ```python
  sum_val = 0
  for idx in range(1, 6):
      sum_val += idx

  print(idx)
  ```

  ```
  5
  ```

    <br/>

  ```python
  n = 10
  if n % 2 == 0:
      k = 5
  else:
      k = 6

  print(k)
  ```

  ```
  5
  ```

<br/>

- 다만 이러한 지역 변수는 다른 함수(<code>for</code>문, <code>if</code>문도 포함)의 내부 영역에선 참조할 수 없다.

  ```python
  def g(n):
      return n + t    # 이 g함수 내부에선, f함수 내부의 t에 접근할 수 없다.

  def f(n, p1):
      t = 15
      return n + p1 + g(10)

  p = 9
  print(f(6, 10))
  ```

  ```
  NameError: name 't' is not defined
  ```

<br/>

- 그러나 코드는 되도록 이렇게 안 짜는 것이 좋다.

<br/><br/>

## range 함수의 이해 (C++ 반복문과 python 반복문의 차이점)

- <code>range(1, 6)</code> == <code>[1, 2, 3, 4, 5]</code> 이렇게 이해하면 편한다. (틀린 설명이나)

<br/>

- C++에서 for문은 변수 i 자체가 값이 1씩 증가하다 조건을 벗어나는 순간, 즉 아래 코드에선 i가 6이 된 직후, 종료한다.

  ```c++
  #include <iostream>
  using namespace std;

  int main() {
      int sum_val = 0;
      int i;

      for (i = 0; i < 6; i++) {
          sum_val += i;
      }

      cout << i;

      return 0;
  }
  ```

  ```
  6
  ```

  <br/>

- 반면 파이썬에서 for문은 변수 i 자리에 1부터 5까지 값이 하나씩 대입되고 끝난다. 즉 i값은 5인 상태가 된다.

  ```python
  sum_val = 0
  for i in range(1, 6):
      sum_val += i

  print(i)
  ```

  ```
  5
  ```

<br/><br/>

## python의 최대 정수값 <code>sys.maxsize</code> 활용하기

- 어떤 리스트 내 정수 원소들의 최댓값 혹은 최솟값을 찾는 프로그램을 내장 함수를 쓰지 않고 직접 구현할 땐, 초깃값을 잘 잡아주어야 한다.

<br/>

- 이 때, 첫 번째 원소를 초갓값으로 잡아주어도 되지만, python의 <code>int</code>의 최댓값인 <code>sys.maxsize</code>를 활용하는 것이 좋다.

- 더불어 python의 <code>int</code>의 최솟값은 여기에 마이너스를 붙여 <code>-sys.maxsize</code>로 구한다.

<br/>

- <code>sys.maxsize</code>를 활용하려면 <code>sys</code> 모듈을 불러와야 한다.

    <br/>

  ```python
  import sys

  INT_MAX = sys.maxsize

  lst = [34, 5, 67, 4, 8, 15, 2]
  max_sum = -INT_MAX  # 초깃값

  for elem in lst:
      if elem > max_sum:
          max_sum = elem
      #max_sum = max(elem, max_sum)

  print(max_sum)
  ```

  ```
  67
  ```

- 위 코드처럼 리스트 내 원소들의 최댓값 찾을 땐, 초기값을 가장 작은 수인 <code>-sys.maxsize</code>로 둔다. (for문을 돌면서 더 큰 값으로 업데이트 할 수 있도록)

    <br/>

  ```python
  import sys

  INT_MAX = sys.maxsize

  lst = [34, 5, 67, 4, 8, 15, 2]
  min_sum = INT_MAX  # 초깃값

  for elem in lst:
      if elem < min_sum:
          min_sum = elem
      #max_sum = max(elem, min_sum)

  print(min_sum)
  ```

  ```
  2
  ```

* 반대로 최솟값을 찾을 땐, 가장 큰 수 <code>sys.maxsize</code>로 초기값을 잡아준다.

<br/><br/>

## TypeError: sequence item 0: expected str instance, int found 해결 (int형 list join하기)

```python
int_list = [1, 2, 3, 4, 5, 6, 7]
result = ''.join(int_list)
# TypeError: sequence item 0: expected str instance, int found
```

- int형의 list를 join하려고 보면 이러한 에러가 생긴다. 뜻을 해석하자면 <strong>join할 때는 string이 들어가야 하나</strong> int가 들어갔다는 것이다.

- 이것을 join하고 싶다면 어떻게 해야 할까?

```python
int_list = [1, 2, 3, 4, 5, 6, 7]
result = ''.join(map(str, int_list))
result_to_int = int(''.join(map(str, int_list)))

print(type(result))
print(result)

print(type(result_to_int))
print(result_to_int)

# <class 'str'>

# 1234567

# <class 'int'>

# 1234567
```

- 그냥 <strong>map 함수를 이용해서 str로 바꿔주면 된다.</strong> 그러면 당연히 합쳐진 1234567은 string 형태를 갖게 되는데, 이를 int 형태로 바꾸고 싶다면 그냥 전체를 int로 씌워주면 된다.

<br/><br/>
