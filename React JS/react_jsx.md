# React JS - JSX (HTML에 요소 만들어 추가하기)

> 참고 자료 : <a href="https://nomadcoders.co/react-for-beginners">노마드 코더 - React JS로 영화 웹서비스 만들기</a>

<br/>

### 목차

- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/React%20JS/react_jsx.md#createelement%EB%A5%BC-%EC%9D%B4%EC%9A%A9%ED%95%9C-%EA%B8%B0%EC%A1%B4%EC%9D%98-%EB%B0%A9%EB%B2%95%EC%9C%BC%EB%A1%9C-html-%EC%9A%94%EC%86%8C-%EB%8B%A4%EB%A3%A8%EA%B8%B0%EC%B6%94%EA%B0%80%ED%95%98%EA%B8%B0"><code>createElement</code>를 이용한 기존의 방법으로 HTML 요소 다루기/추가하기</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/React%20JS/react_jsx.md#jsx">JSX</a>
  - <a href="https://github.com/SangYoonLee1231/TIL/blob/main/React%20JS/react_jsx.md#createelement-vs-jsx"><code>createElement</code> vs JSX</a>
  - <a href="https://github.com/SangYoonLee1231/TIL/blob/main/React%20JS/react_jsx.md#babel">Babel</a>
  - <a href="https://github.com/SangYoonLee1231/TIL/blob/main/React%20JS/react_jsx.md#%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8-%EC%83%9D%EC%84%B1--%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8%EB%A5%BC-%EB%8B%A4%EB%A5%B8-%EC%BB%B4%ED%8F%AC%EB%84%8C%ED%8A%B8%EC%97%90-%EB%84%A3%EA%B8%B0">컴포넌트 생성 & 컴포넌트를 다른 컴포넌트에 넣기</a>

<br/><br/>

## <code>createElement</code>를 이용한 기존의 방법으로 HTML 요소 다루기/추가하기

- <strong>구현 목표</strong>

    <img src="img/react_jsx1.png">

  - 1.&nbsp;&nbsp;<code>Hello I'm a span</code>에 마우스 닿을 시, 콘솔 창에 <code>mouse enter</code> 문구 표시

  - 2.&nbsp;&nbsp;<code>Click me</code> 버튼 클릭 시, 콘솔 창에 <code>i clicked</code> 문구 표시

 <br/>

- <strong>Vanila JS</strong> 이용 + <code>createElement</code> 함수 활용

  ```html
  <!DOCTYPE html>
  <html lang="en">
    <body>
      <h3 id="text">Hello. I'm a span.</h3>
      <button id="btn">Click Me</button>
    </body>
    <script>
      const text = document.getElementById("text");
      const button = document.getElementById("btn");
      text.id = "title";
      button.style.backgroundColor = "tomato";
      function handleClick() {
        console.log("i clicked");
      }
      function handleMouseEnter() {
        console.log("mouse enter");
      }
      button.addEventListener("click", handleClick);
      text.addEventListener("mouseenter", handleMouseEnter);
    </script>
  </html>
  ```

<br/>

- <strong>React JS</strong> 이용 + <code>createElement</code> 함수 활용

  ```html
  <!DOCTYPE html>
  <html lang="en">
    <body>
      <div id="root"></div>
    </body>
    <script src="https://unpkg.com/react@17.0.2/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@17.0.2/umd/react-dom.development.js"></script>
    <script>
      const root = document.getElementById("root");
      const title = React.createElement(
        "h3",
        {
          id: "title",
          onMouseEnter: () => console.log("mouse enter"),
        },
        "Hello. I'm a title."
      );
      const btn = React.createElement(
        "button",
        {
          onClick: () => console.log("i clicked"),
          style: {
            backgroundColor: "tomato",
          },
        },
        "Click Me"
      );
      const container = React.createElement("div", null, [h3, btn]);
      ReactDOM.render(container, root);
    </script>
  </html>
  ```

<br/>

- <strong>React JS</strong>를 이용하는 것이 Vanila JS를 이용하는 것보다 <strong>더 편리함</strong>을 확인할 수 있다.

  - <strong>JS에서 직접 HTML 요소를 생성</strong>한 후 <strong>필요한 기능을 한 번에 붙인 뒤</strong> HTML에 삽입하기만 하면 되므로

- 하지만 <code>createElement</code>를 사용한 위 두 방법보다 <strong>더 편리하게</strong> HTML 요소를 만들어 넣는 방법이 있다.

  => <strong>JSX</strong>

<br/><br/>

## JSX

- <strong>JSX</strong>는 Javascript를 확장한 문법이다.

- HTML 문법과 같은 규칙을 사용한다.

<br/>

### <code>createElement</code> vs <strong>JSX</strong>

- <code>createElement</code>로 작성된 코드와 <strong>JSX</strong> 문법으로 작성된 코드를 서로 비교해보면 <strong>JSX</strong> 문법의 강력함을 알 수 있다.

  - 예시 1

    - <code>createElement</code>

      ```javascript
      const title = React.createElement(
        "h3",
        {
          id: "title",
          onMouseEnter: () => console.log("mouse enter"),
        },
        "Hello. I'm a title."
      );
      ```

    - <strong>JSX</strong>

      ```javascript
      const title = (
        <h3 id="title" onMouseEnter={() => console.log("mouse enter")}>
          Hello I'm a title
        </h3>
      );
      ```

  <br/>

  - 예시 2

    - <code>createElement</code>

      ```javascript
      const btn = React.createElement(
        "button",
        {
          onClick: () => console.log("i clicked"),
          style: {
            backgroundColor: "tomato",
          },
        },
        "Click Me"
      );
      ```

    - <strong>JSX</strong>

      ```javascript
      const btn = (
        <button
          style={{
            backgroundColor: "tomato",
          }}
          onClick={() => console.log("i clicked")}
        >
          Click Me
        </button>
      );
      ```

<br/>

- JSX 문법은 HTML과 유사하나 다른 점도 존재함을 기억해야 한다.

  - <code>class</code>나 <code>for</code>같은 키워드는 React JS에서 제대로 동작하지 않을 수 있다.

    (<code>class</code> => <code>className</code>, <code>for</code> => <code>htmlFor</code>을 써야 한다.)

<br/>

- JSX 문법으로 작성한 JS 코드는 브라우저가 바로 이해할 수 없기 때문에, 브라우저가 이해할 수 있는 형태로 변환해주는 장치가 필요하다.

  => <strong>Babel</strong>

<br/><br/>

### Babel

- JSX로 적은 코드를 브라우저가 이해할 수 있는 형태로 바꿔주는 장치

- <a href="https://babeljs.io/">Babel 홈페이지 바로가기</a>

  <br/>

- Babel standalone를 이용하여 변환기 설치하기

  - HTML에 다음을 삽입한다.

    ```html
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    ```

  - 그리고 JS 코드를 작성할 때 script 태그의 속성(property)에 <code>type="text/babel"</code>를 부여해준다.

    ```html
    <script type="text/babel">
      // JS 코드를 작성하는 곳
    </script>
    ```

  - 이 방식은 느리기 때문에 혼자할 때는 절대 이렇게 할 일이 없을 것이다. 이보다 더 나은 방식이 있다.

<br/><br/>

### 컴포넌트 생성 & 컴포넌트를 다른 컴포넌트에 넣기

- element를 태그로 묶어 다른 곳에 사용하려면, <strong>element를 컴포넌트(함수형)로 바꿔주어야 한다.</strong>

  (이 때 <a href="https://github.com/SangYoonLee1231/TIL/blob/main/JavaScript/javascript_piece_info.md#%ED%99%94%EC%82%B4%ED%91%9C-%ED%95%A8%EC%88%98-array-function">화살표 함수</a>를 이용한다.)

- <strong>컴포넌트</strong>란 JSX를 반환하는 함수이다. (<strong>함수형 컴포넌트</strong>)

- 일반 element를 <strong>함수형</strong>으로 바꾸면 <strong>컴포넌트</strong>(사용자 정의 태그)로 인식된다.

<br/>

- ✨ 직접 만든 컴포넌트를 렌더링해서 다른 곳에 사용할 때는 이름이 <strong>항상 대문자로 시작</strong>되어야 한다.

  ```javascript
  const root = document.getElementById("root");

  const Title = () => (
    <h3 id="title" onMouseEnter={() => console.log("mouse enter")}>
      Hello I'm a title
    </h3>
  );

  const Btn = () => (
    <button
      style={{
        backgroundColor: "tomato",
      }}
      onClick={() => console.log("i clicked")}
    >
      Click Me
    </button>
  );

  // Title, Btn, Container와 같이 이름이 대문자로 시작해야 컴포넌트로 바르게 인식된다.
  const Container = () => (
    <div>
      <Title />
      <Btn />
    </div>
  );

  ReactDOM.render(<Container />, root);
  ```

<br/>

- ✨ 컴포넌트를 리렌더링 시, 전체를 전부 재생산하지 않고 전과 달리진 부분만 새로 생성한다.
