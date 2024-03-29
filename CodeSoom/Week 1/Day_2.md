# 1주차 Day 2 TIL

#### 2022.08.02

<br/>

## 공부한 것 (간략히 정리)

### 【1】 ESLint (마무리)

- <code>ReferenceError: primordials is not defined</code> 오류 해결

    - NVM으로 Node와 NPM 버전을 계속 바꿔봐도 오류 여전히 발생

    - 그래서 수동으로 코드를 삽입하기로 결정

    - <a href="https://triplexlab.tistory.com/40">해당 포스트</a>에서 <code>.eslintrc.js</code> 코드를 복붙하였으나 실패

    - <code>npx eslint src/index.js</code> 명령어 입력 시 뜨는 터미널 에러 메세지를 관찰하다가 <strong>해결 방법을 찾음</strong>

    - 아래의 5개의 명령어를 입력해 수동 설치 함
        
        - <code>npm install eslint-config-airbnb</code>

        - <code>npm install eslint-plugin-react</code>

        - <code>npm install eslint-plugin-jsx-a11y@latest --save-dev</code>

        - <code>npm install eslint-plugin-import@latest --save-dev</code>

    - <strong>드디어 정상 작동함.</strong>

    <br/>

    - ESLint 관련 유용한 명령어 정리

        - <code>npx eslint [검사할 파일 위치]</code> : 해당 파일을 코드 스타일 검사

        - <code>npx eslint --fix .</code> : 코드 스타일 자동 수정


<br/><br/>

### 【2】 DOM (문서 객체 모델) 기본적인 개념

- <strong>DOM 이란</strong>

    - Document Object Model

    - HTML, XML과 같은 웹 문서의 구조화된 형태, 객체지향 표현

    - 브라우저가 이해할 수 있는 웹 문서의 형태

        - 브라우저 렌더링 엔진 : 웹 문서 로드, 파싱 => DOM로 구성 => 메모리에 적재

    - 페이지 콘텐츠는 DOM이란 객체 트리 구조로 표현되어, 자바스크립트를 통해 접근 및 조작될 수 있다. (동적으로 조작이 가능하다)

        - 그래서 DOM은 DOM Tree 라고도 한다.

    <br/>

    - 브라우저마다 구현된 DOM이 다르지만, 표준 규약에서 제공하는 공통적인 기능 또한 존재한다.

    - DOM은 JS와 밀접한 관계를 초창기엔 가졌으나 시간이 흐르면서 JS와 독립적으로 발전하였다.

    <br/>

    - <strong>DOM API이란</strong>

        - API = Application Programming Interface

        - JS에서 메모리상에 존재하는 DOM에 접근하여 이를 변경할 수 있도록 하는 모든 프로퍼티와 메소드의 집합 => JS 객체로 묶어 제공

        - DOM API 대표적인 종류
            - <code>document.getElementById(ID 속성값)</code>
            - <code>document.querySelector(CSS 셀렉터)</code>
            - <code>document.getElementsByClassName(클래스 이름들)</code>
            - <code>document.getElementsByTagName(태그명)</code>
            - <code>document.querySelectorAll(CSS 셀렉터)</code>
            - <code>parentNode.appendChild(노드)</code>
            - <code>element.innerHTML</code>
            - 등등..

<br/><br/>

### 【3】 Vanila JS로 HTML 요소 만들어 삽입하기

- HTML 파일에 태그를 직접 작성한 후 이를 JS로 가져오는 방식이 아닌,  

    React JS처럼 처음부터 모든 태그를 JS에서 만들고 이를 HTML에 넣는 방식으로 코드를 작성할 수 있다.  

     (처음으로 경험했음)

<br/>

- 새로 알게 된 DOM API

    - <code>createTextNode</code>

<br/>

- ➕ Step 1

    ```javascript
    const container = document.getElementById('app');

    const paragraph1 = document.createElement('p');
    const text1 = document.createTextNode('Hello World!!!');
    const text2 = document.createTextNode('Hello World!!!!!');
    paragraph1.appendChild(text1);
    paragraph1.appendChild(text2);
    container.appendChild(paragraph1);

    const paragraph2 = document.createElement('p');
    const text3 = document.createTextNode('Hi!!!');
    paragraph2.appendChild(text3);
    container.appendChild(paragraph2);
    ```

<br/>

- ➕ Step 2

    ```javascript
    function createElement(tagName, ...children) {
    const element = document.createElement(tagName);

    children.forEach((child) => {
        element.appendChild(child);
    });

    return element;
    }

    //

    const paragraph1 = createElement(
    'p',
    document.createTextNode('Hello World!!!'),
    document.createTextNode('Hello World!!!!!'),
    );

    const paragraph2 = createElement(
    'p',
    document.createTextNode('Hi!!!'),
    );

    //

    const root = createElement(
    'div',
    paragraph1,
    paragraph2,
    );
    const container = document.getElementById('app');

    container.appendChild(root);

    ```
<br/>

- ➕ Step 3

    ```javascript
    function createElement(tagName, ...children) {
        const element = document.createElement(tagName);

        children.forEach((child) => {
            element.appendChild(child);
        });

        return element;
    }

    //

    document.getElementById('app').appendChild(
        createElement(
            'div',
            createElement(
                'p',
                ...['!!!', '!!!!!'].map((c) => document.createTextNode(`Hello World${c}`)),
            ),
            createElement(
                'p',
                document.createTextNode('Hi!!!'),
            ),
        ),
    );

    ```

<br/>

- <strong>아직 익숙치 않아 간단히 정리해본 <code>forEach</code>, <code>map</code>, <code>filter</code>, <code>... (전개 구문)</code> 문법</strong>

    ```javascript
    numList = [1, 2, 3, 4, 5];

    // forEach : 리스트 각각의 요소에 대해 실행
    console.log( numList.forEach((item) => console.log(`Hello ${item}`)) );

    // map : 새 요소 값으로 배열 반환
    console.log( numList.map((item) => item * 2) );

    // filter : 조건에 맞는 요소만 배열에 담아 반환
    console.log( numList.filter((item) => item > 3) );

    // ... (전개구문) : 배열이나 객체의 요소를 말 그대로 전개
    console.log([...numList, 6]);
    ```
    ```
    [forEach 결과]
    Hello 1
    Hello 2
    Hello 3
    Hello 4
    Hello 5

    [map 결과]
    [2, 4, 6, 8, 10]

    [filter 결과]
    [4, 5]

    [... (전개구문) 결과]
    [1, 2, 3, 4, 5, 6]
    ```

<br/><br/>

## 과제 진행

(진행하지 못함)

<br/><br/>

## Feeling

- 드디어 어제 그렇게나 날 괴롭혔던 ESLint 초기화 문제를 해결했다. 터미널에서 일일이 패키지를 설치했더니 다행히도 정상적으로 작동되었다. 해결 과정은 비록 험난었지만, 막상 해결이 되니 뭔가 좀 허무한 기분이 들었다.

- 하지만 어제와 오늘의 고생이 모두 나에게 피가 되고 살이 되었다는 것을 알기에, 충분히 의미있는 고생이었다고 생각한다. 이런 좋은 경험을 할 수 있어 감사히다.

    - (덕분에 공식 문서와 Stack Overflow를 찾아보는 것이 좀 더 익숙해지기도 했고 말이다.)

<br/>

- 오늘 아침에는 코테 대비 캠프 수업, 오후에는 캠프 과제 수행 및 어제 발목을 잡았던 오류 해결로 인해 실질적인 진도는 저녁부터 나갈 수 있었다.

- 그로 인해 오늘 또한 과제를 하지 못했고, PR 또한 보내지 못했다. <strong>하지만 어제와 달리, 내 마음은 편안했다.</strong>  
 그 이유는 내가 게으름을 피워서 과제를 못한 것이 아니라는 걸 알았기 때문이다.

<br/>

- 어제자 TIL을 코드숨 리엑트 11기 채널에 공유했는데, 오늘 대표님께서 제 걱정스런 마음을 보시고 <code>만일 정말 최악의 상황이 벌어진다면 어떤 일이 일어날까요?</code> 라는 질문을 던져주셨다.

- 왜 이런 질문을 하셨을까. 처음엔 좀 의아했는데, 곰곰히 생각해보니 한 번 최악의 상황을 스스로 생각해 봄으로써 내 걱정의 실체를 스스로 돌아볼 수 있도록 하신 것이 아닐까 싶었다.

<br/>

- 나는 성장에 목마르다. 이를 위해선 어떤 고통도 감내할 자신이 있다.  
하지만 부족한 베이스로 인해 진도가 생각보다 더 느려지니, 결국 첫 날 코드 리뷰의 기회를 놓쳐버렸다.  
더불어 내가 주어진 기간 내에 모든 내용과 과제를 충분히 소화할 수 있을지도 걱정이 들기 사작했다.    

- 내가 베이스가 부족하다는 점은 교육 시작 전부터 걱정이 되는 부분이었는데, 결국 이 부분이 이렇게 발목을 잡게 되는 것 같아 마음에 어려움이 왔다.  

<br/>

- 하지만 이 때 문득 든 생각이, 내가 매일매일을 최선을 다해 공부하고 있다고 자부할 수 있으면 성장은 당연히 이뤄지는 게 아닌가 하는 생각이었다.

- 나는 베이스가 부족하지만 직장에 다니시는 분들보단 시간적 여유가 많다.  
그렇기에 남들보다 더 많이 공부해서 어떻게든 교육을 소화해보자고 마음 먹고 코드숨을 시작했다. 

- 그리고 그 마음에 따라 오늘도 최선을 다해 공부했다. <strong>그럼 지금 이미 충분히 잘하고 있는 거 아닌가.</strong>  
그런 생각이 드니 걱정의 이유 또한 사라져버렸다.

- <strong>그래. 나는 지금 이미 충분히 잘하고 있다.</strong> 다만 공부하는 데 시간이 좀 더 오래 걸릴 뿐.  
<strong>그러니 더 이상 불안해하지 말고 어제 오늘처럼 열심히 공부하자</strong>.  
그럼 성장은 자연히 따라올테니.

<br/>

<img src="img/codesoom-day-1-question.png">

    
