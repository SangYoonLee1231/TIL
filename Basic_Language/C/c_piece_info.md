# C / C# / C++ - 조각 지식 모음

<br/>

- C계열 언어와 관련된 공부 내용 중 하나의 목차로 분류하기 애매한 지식을 따로 모아 정리하는 곳입니다.

<br/>

### 목차

- <a href="">Type 자동 변환</a>
<!-- - <a href=""></a> -->

<br/>

## Type 자동 변환

- C계열 언어에서 사칙연산 계산시 type은 더 큰 범위를 따라가게 되어있다.

  - 정수와 실수가 피연산자로 만나면, 계산 결과의 type은 실수가 된다.

    ```c++
    double a = 1 + 3.5;
    cout << a; // 4.5
    ```

<br/><br/>

## 자료형 선언은 절대적인 것이 아니다.

- 자료형 선언을 실수로 했더라도 계산 결과가 정수이면 출력값 또한 정수가 된다.

```c++
#include <iostream>
using namespace std;

int main()
{
	double a = 3 / 3;

  cout << a << endl; // 1

	return 0;
}
```
