# 4주차 Day 2 TIL

#### 2022.08.23

<br/>

## 배운 것 (간략히 정리)

### 【1】 테스트 코드 추가 실습 (지난 과제)

- 테스트 코드를 좀 더 숙달하기 위해 지난 주 과제를 다시 진행했다.

    - 코드를 지우고 다시 써보거나..
    
    - test 구문으로 작성된 코드를 BDD (<code>describe</code>-<code>context</code>-<code>it</code>) 스타일로 바꿔보거나..

<br/>

- 덕분에 BDD 스타일로 테스트 코드를 작성하는 것에 더욱 친숙해졌다.

<br/>

- 추가로 알게 된 점

    - <code>npx jest --watchAll --verbose</code> : 테스트 결과를 계층적으로 확인하고 싶을 때 실행하는 명령문
    
<br/>

### 【2】 Flux 아키텍처와 Redux 이어 학습

- <strong>Flux Architecture</strong>

    - 추상적 개념. 단방향으로 데이터 흐름을 관리하는 패턴.

    - [Action] -> [Dispatcher] -> [Store] -> [View]

    - [View] -> [Action] -> [Dispatcher] -> [Store] -> [View]

<br/>

- <strong>Redux</strong>

    - 페이스북에서 Flux 아키텍트를 구현한 라이브러리

    - React 어플리케이션에서 state 관리를 할 때 사용되는 '상태관리' 라이브러리

    <br/>

    - <strong>Redux 3가지 원칙</strong>

        - 전체 상태값을 하나의 객체 (Store) 에 저장한다.

        - 상태값은 불변 객체이다.

        - 상태값은 순수 함수에 의해서만 변경되어야 한다.

    <br/>

    - Action, Reducer, Store, Provider, react-redux hook

<br/>

- Redux가 무엇인지 대략적인 감을 잡았으나, 아직 알아야 할 것이 훨씬 더 많아보인다.

- (그나저나 한글 버전 Flux 공식 문서는 외계어 같다.)

- 그래서 늘 하던 대로 따로 개인 학습을 진행하기로 했다.

<br/>

### 【2】 Redux 개인 학습 - 생활 코딩

#### Redux 소개
    
- <strong>Redux</strong>

    - JS 앱을 위한, 예측가능한 상태의 저장소

    - 코드의 복잡성을 획기적으로 낮춰줌으로써, 결과를 예측 가능하게 만들어주는 도구

    <br/>

    - 단 하나의 상태(객체)를 갖는다. <- 앱의 모든 데이터를 우겨넣음
    
        - 앱의 복잡성 낮춤

    - 데이터를 외부에서 직접적으로 제어할 수 없음 (정보 은닉과 비슷한 개념)

        - 의도하지 않게 state 값이 변하는 것을 차단 -> 앱을 예측가능하게 만듦

<br/>

- <strong>가능성</strong>

    - Undo와 Redo를 굉장히 쉽게 할 수 있다.

        - 각각의 상태 변화가 서로에게 영향을 주지 않음 (원본을 직접 변화하지 않기 때문)

    - 앱의 과거 상태도 쉽게 알 수 있어 문제 해결을 쉽게 할 수 있도록 도와준다.

    - 모듈 리로딩 - 코드 작성 시 자동으로 앱에 반영

        - 앱은 새로고침 되어도 데이터는 그대로 남아있기 때문


<br/><br/>

## 과제 진행

(진행하지 못함)

<br/><br/>

## Feeling

- 코로나 약으로 인해 오늘도 엄청 잤다.

- 코로나 여파가 너무 심한거 아니냐.. 내일은 좀 괜찮았으면 좋겠다.

- 그래도 지금까지 주어진 상황 속에서 잘 하고 있다고 생각한다. 그러니 내일 다시 열심히 해보자.