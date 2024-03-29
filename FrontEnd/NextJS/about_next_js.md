# Next JS란?

> 참고 자료 : <a href="https://www.inflearn.com/course/lecture?courseSlug=%EB%94%B0%EB%9D%BC%ED%95%98%EB%8A%94-%EB%A0%88%EB%94%A7&unitId=123111&tab=curriculum">인프런 - 따라하며 배우는 노드, 리액트 시리즈 - 레딧 사이트 만들기(NextJS) (John Ahn님)</a>

<br/>

### 목차

- <a href="">Next JS란?</a>

  - <a href="">Next JS의 특징</a>
  - <a href="">Next JS 설치</a>

- <a href="">Next JS 기본 파일 구조</a>

  - <a href="">`pages`</a>
  - <a href="">`public`</a>
  - <a href="">`styles`</a>

- <a href="">Pre-Rendering</a>
- <a href="">Data Fetching</a>
  <!-- - <a href=""></a> -->
  <!-- - <a href=""></a> -->

<br/><br/>

## Next JS란?

- React에서 <strong>SSR(Server Side Rendering)</strong>을 쉽게 구현할 수 있도록 도와주는 간단한 <strong>프레임워크 (Framework)</strong>이다.

<br/>

> < <strong>Framework VS Library</strong> >
>
> <strong>공통점</strong> : 복잡한 개발을 편리하게 할 수 있도록, 필요한 기능들을 미리 만들어 사용할 수 있는 형태로 제공된 코드
>
> <strong>차이점</strong> : <strong>Framework</strong>은 전체적인 틀(Frame)을 제공해주기 때문에, 개발자가 그 틀 안에서 그 방식에 맞춰 작업을 해야만 한다. / 반면 <strong>Library</strong>는 하나의 기능만을 도구로써 제공해주기 때문에, 개발자 본인이 필요한 여러 도구들을 직접 가져와서 조립히여 사용해야 한다.

<br/>

- 리엑트로 개발할 땐 SPA(Single Page Application)를 이용하여 CSR(Client Side Rendering)을 하지만, 이 방식은 검색 엔진 최적화(SEO) 부분에서 단점이 존재한다.

  - 왜 이러한 단점이 있는지는 <a href="https://github.com/SangYoonLee1231/TIL/blob/main/NextJS/ssr_vs_csr.md">여기</a>를 참고하여 짚고 넘어가자.

<br/>

### Next JS의 특징

- NextJS는 Framework이므로, Library와 달리 **렌더링 과정**을 사용자가 직접 다루지 못한다. (ReactJS는 Library)

- <strong>pages 폴더 안에 있는 파일명에 따라 route가 결정된다.</strong>

  - `pages/about.js` → localhost:3000/about
  - `pages/index.js` → localhost:3000 (예외사항)

- JSX를 쓰고 있다면, React를 import하지 않아도 된다.

  - 그러나 useState나 useEffect와 같은 react 메소드를 쓰고 싶다면 React를 import 해주어야 한다.

<br/>

### Next JS 설치

- `npx create-next-app@latest`

- 타입스크립트를 사용한다면 `npx create-next-app@latest --typescript`

- 현재 디렉토리에 설치하려 한다면 `npx create-next-app@latest --typescript./`

<br/><br/>

## Next JS 기본 파일 구조

- (설치 시 src 폴더를 생성하지 않는다고 설정했음을 가정한다)

  <div align="center">

    <img src="img/nextjs-file-structure.png" width="120">

  </div>

<br/>

### pages

- 페이지들을 생성하는 폴더

  - 페이지 이름에 `.jsx`, 타입스크립트를 쓴다면 `.tsx`를 붙여 페이지를 생성한다.

  - `about` 페이지 생성 → `about.jsx` 혹은 `about.tsx`

- `_app.tsx` : 페이지의 공통된 레이아웃을 작성하는 곳

  - 특정 페이지로 진입하기 전에 먼저 통과하는 인터셉터 페이지이다.

  - 즉, 이 곳에서 렌더링 하는 값은 모든 페이지에 적용된다.

- `document.tsx` : meta 태그를 정의하거나, 전체 페이지에 관여하는 컴포넌트이다.

- `index.tsx` : 앱의 첫 `"/"`(루트) 페이지

<br/>

### public

- 정적 에셋들을 보관하는 폴더

  - 예 : 이미지

<br/>

### styles

- CSS 스타일링을 처리해주는 폴더

- 글로벌 스타일은 `_app.tsx`에서만 정의해줄 수 있다.

- 컴포넌트에 종속적으로 스타일링을 주기 위해 모듈(module) CSS를 사용할 수 있다.

  - `index.tsx`(홈 컴포넌트)에 종속적으로 스타일링을 해주려면 `Home.module.css` 파일명을 이 폴더에 만들고, 이 파일에 CSS 코드를 삽입하면 된다.

<br/>

- NextJS는 webpack을 기본 번들러로 사용한다.

- 그래서 webpack 관련 설정들은 `next.config.js`에서 한다.

<br/><br/>

## Pre-Rendering

- Pre-Rendering이란, Client Side에서 JavaScript로 모든 UI를 생성하지 않고, 대신 각 페이지의 HTML을 사전에 미리 생성하는 방식을 말한다.

- 이 작업 덕분에 Next 앱은 SEO에서 더 나은 성능을 보여줄 수 있다.

<br/>

- NextJS는 모든 페이지를 Pre-Render한다.

- Pre-Rendering된 Next 앱은 서버에서 미리 만들어지기 때문에 JS 기능을 사용하지 않더라도 브라우저 화면에서 잘 동작한다.

  - (React는 CSR 방식으로 JS가 UI를 만들어주기 때문에, JS 기능을 끄면 앱이 정상적으로 동작하지 않는다.)

<br/>

#### Pre-Rendering에는 2가지 과정이 있다.

- **Initial Load** : 서버 측에서 웹 페이지를 사전 렌더링하는 단계

  - JS 파일이 로드되기 전이므로 웹 UI(HTML)만 나타난다.

- **Hydration** : 클라이언트 측에서 초기 로드된 정적 HTML을 가져와 브라우저에서 동적으로 구성되는 단계

  - JS와 HTML이 연결되어 페이지와 유저가 상호작용할 수 있게 된다.

<br/>

#### Pre-Rendering에는 2가지 종류가 있다.

- <strong>SSG (Static Side Generation)</strong>

  - 빌드 시, pages 폴더에서 작성한 각 페이지들에 대해 각각의 문서를 static한 파일로 생성한다.

  - HTML을 빌드 타임에 생성하고, 요청 시마다 재사용한다.

- <strong>SSSR (Server-Side Rendering)</strong>

  - 유저가 HTML을 요청할 때마다 그에 맞는 HTML 문서를 생성해서 반환한다.

<br/><br/>

## Data Fetching

- Data Fetching은 말 그대로 **데이터를 가져오는 것이다.**

- NextJS에서 데이터를 가져오는 방법은 여러가지가 있다.

- 앱의 사용 용도에 따라 맞는 방법을 택해 사용하자.

<br/>

#### Next JS 13 버전에선 `async`/`await`을 통한 `fetch()` API를 사용한다.

<br/>

#### 13 버전 이전 방식은 다음과 같다.

- <strong>SSG (Static Side Generation)</strong>

  - `getStaticProps`, `getStaticPaths`, `getServerSideProps`

- <strong>SSR (Server Side Rendering)</strong>

  - `getServerSideProps`

<br/>

<!-- #### 1. `getStaticProps`

- -->

<!-- <br/>

#### 2. `getStaticPaths`

<br/> -->
<!--
#### 3. `getServerSideProps`

<br/> -->
