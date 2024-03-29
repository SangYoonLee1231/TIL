# Python - 튜플 vs 딕셔너리 vs 집합

<br/>

## 목차

- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Python/python_tuple_dict_set.md#%ED%8A%9C%ED%94%8C-tuple">튜플 (tuple)</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Python/python_tuple_dict_set.md#%EB%94%95%EC%85%94%EB%84%88%EB%A6%AC-dictonary">딕셔너리 (dictonary)</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Python/python_tuple_dict_set.md#%EC%A7%91%ED%95%A9-set">집합 (set)</a>

<br/><br/>

## 튜플 (tuple)

- 리스트와 거의 비슷한 자료형이나, 몇 가지 차이점이 존재한다.

  - <code>()</code>으로 둘러싼다.

  - 내부 요소 값을 지우거나 변경할 수 없다.

    ```python
    t1 = ()
    t2 = (1, )  # 요소가 1개일 때는 반드시 콤마를 붙어주어야 한다.
    t3 = (1, 2, 3)
    t4 = 1, 2, 3  # 괄호를 생략해도 된다.
    t5 = ('a', 'b', (1, 2))
    ```

  - 튜플로 인덱싱, 슬라이싱, 더하기, 곱하기, 길이 구하기 모두 가능하다. (리스트와 동일)

<br/><br/>

## 딕셔너리 (dictonary)

- <code>Key</code>값과 <code>Value</code>값이 서로 쌍으로 이루어진 연관 배열(해시)이다.

- <code>{}</code>로 둘러싼다.

- 순서가 없는 자료형이라 인덱싱을 지원하지 않는다.

<br/>

- dictonary 예제 코드

  ```python
  dict = {
      'name': 'SYL',
      'age': 25,
      'gender': 'male'
      'tech-stack': ['python', 'javascript', 'c++', 'java']
  }
  ```

  ```python
  >>> dict['name']
  'SYL'
  >>> dict[age]
  25
  >>> 'name' in dict
  True
  >>> 'email' in dict
  False
  ```

  ```python
  >>> dict.keys()
  dict_keys(['name', 'age', 'gender', 'tech-stack])
  >>> dict.values()
  dict_values(['SYL', 25, 'male', ['python', 'javascript', 'c++', 'java']])
  >>> dict.items()
  dict_items([
    ('name': 'SYL'),
    ('age': 25),
    ('gender': 'male'),
    ('tech-stack': ['python', 'javascript', 'c++', 'java'])
  ])
  ```

- 딕셔너리에서 <code>Key</code>는 고유한 값이다.

- <code>Key</code>에는 imutable한 값만 쓸 수 있고, <code>Value</code>에는 아무 값이나 넣을 수 있다.

<br/><br/>

## 집합 (set)

- 집합에 관련된 것을 쉽게 처리하기 위해 만들어진 자료형이다.

- 딕셔너리와 마찬가지로 <code>{}</code>로 둘러싼다.

- 딕셔너리와 마찬가지로 순서가 없는 자료형이라 인덱싱을 지원하지 않는다.

- 집합은 중복을 허용하지 않는다.

<br/>

- 집합을 초기화 할 때, 즉 빈 set을 만들려 할 때, `{}`을 사용하여 초기화를 해선 안된다. 이는 빈 딕셔너리가 생성되는 것이지, 빈 집합(set)이 생성되는 것은 아니다.

- 빈 set을 만들기 위해서는 `set()` 생성자를 사용해야 한다.

  ```python
  empty_set = set()
  ```

<br/>

- set 예제 코드

  ```python
  s0 = set()
  s1 = set([1, 2, 3])
  s2 = set(["Hello"])
  ```

  ```python
  >>> s0
  {}
  >>> s1
  {1, 2, 3}
  >>> s2
  {'e', 'H', 'l', 'o'}
  ```

  ```python
  s1 = set([1, 2, 3, 4, 5, 6])
  s2 = set([4, 5, 6, 7, 8, 9])
  ```

  ```python
  # 교집합
  >>> s1 & s2
  {4, 5, 6}
  >>> s1.intersection(s2)
  {4, 5, 6}

  # 합집합
  >>> s1 | s2
  {1, 2, 3, 4, 5, 6, 7, 8, 9}
  >>> s1.union(s2)
  {1, 2, 3, 4, 5, 6, 7, 8, 9}

  # 차집합
  >>> s1 - s2
  {1, 2, 3}
  >>> s2 - s1
  {8, 9, 7}
  >>> s1.difference(s2)
  {1, 2, 3}
  >>> s2.difference(s1)
  {8, 9, 7}
  ```

- 집합 관련 함수들

  - <code>add</code> : 값 1개 추가하기

    - <code>s1.add(4)</code>

  - <code>update</code> : 값 여러개 추가하기

    - <code>s1.update([4, 5, 6])</code>

  - <code>remove</code> : 특정 값 제거하기

    - <code>s1.remove(2)</code>

 <br/>

- set는 <code>x in s</code> 연산이 list보다 훨씬 빠르다. (O(n) vs O(1))

  - 파이썬에서 set는 <strong>해시 테이블(Hash Table)</strong>로 구현되었기 때문

  <br/>
