## ✨ Fork한 코드숨 과제 Repository - 작업 세팅 순서

<br/>

### 개발 환경 구축

1. 경로 이동 : <code>cd react-week?-assignment-?</code>

2. NPM 초기화 : <code>npm init -y</code>

<br/>

3. Webpack 설치 및 업데이트

   - <code>npx webpack serve --mode development</code> (모두 설치)

   - <code>npm install -D webpack-dev-server</code>

4. ESLint 업데이트 : <code>npm i -D eslint</code>

5. ESLint 설정 : <code>npx eslint --init</code>

<br/>

6. webpack 서버 띄울 시 경로 설정 바뀌어 있는지 확인 (<code>index.js</code>=><code>index.jsx</code>)

   ```js
   // webpack.config.js
   const path = require("path");

   module.exports = {
     entry: path.resolve(__dirname, "src/index.jsx"),
     mode: "development",
     module: {
       rules: [
         {
           test: /\.jsx?$/,
           exclude: /node_modules/,
           use: "babel-loader",
         },
       ],
     },
     resolve: {
       extensions: [".js", ".jsx"],
     },
   };
   ```

<br/>

7. <code>.eslintrc.js</code> 파일 수정

   ```javascript
   // .eslintrc.js
   module.exports = {
     env: {
       browser: true,
       es2021: true,
       jest: true,
     },
     extends: ["plugin:react/recommended", "airbnb"],
     parserOptions: {
       ecmaFeatures: {
         jsx: true,
       },
       ecmaVersion: 12,
       sourceType: "module",
     },
     plugins: ["react"],
     globals: {
       Atomics: "readonly",
       SharedArrayBuffer: "readonly",
       actor: "readonly",
       Feature: "readonly",
       Scenario: "readonly",
     },
     rules: {
       "linebreak-style": 0,
       indent: ["error", 2],
       "no-trailing-spaces": "error",
       curly: "error",
       "brace-style": "error",
       "no-multi-spaces": "error",
       "space-infix-ops": "error",
       "space-unary-ops": "error",
       "no-whitespace-before-property": "error",
       "func-call-spacing": "error",
       "space-before-blocks": "error",
       "keyword-spacing": ["error", { before: true, after: true }],
       "comma-spacing": ["error", { before: false, after: true }],
       "comma-style": ["error", "last"],
       "comma-dangle": ["error", "always-multiline"],
       "space-in-parens": ["error", "never"],
       "block-spacing": "error",
       "array-bracket-spacing": ["error", "never"],
       "object-curly-spacing": ["error", "always"],
       "key-spacing": ["error", { mode: "strict" }],
       "arrow-spacing": ["error", { before: true, after: true }],

       "react/prop-types": "off",
       "react/react-in-jsx-scope": "off",
       "react/jsx-no-bind": "off",
     },
   };
   ```

<br/>

### 테스트 환경 구축

8. Jest 설치 : <code>npm i -D jest @types/jest babel-jest</code>

9. jest-environment-jsdom 설치 : <code>npm i -D jest-environment-jsdom</code>

<br/>

10. <code>jest.config.js</code> 파일을 만들어 아래 코드를 추가

        - jest.config.js

            ```js
            {
                testEnvironment: 'jsdom',
            };
            ```

    <br/>

11. React testing libraty 설치 : <code>npm i -D @testing-library/react @testing-library/jest-dom</code>

<br/>

#### 테스트 환경 추가 작업 : 모든 테스트 파일에 적용할 코드 설정하기

12. <code>jest.config.js</code> 파일에 다음 코드를 추가

    ```js
    // jest.config.js
    module.exports = {
      setupFilesAfterEnv: ["./jest.setup"],

      // ...
    };
    ```

<br/>

13. <code>jest.setup.js</code> 파일을 <strong>생성</strong>하고, 모든 테스트 파일에 적용할 코드를 그 안에 작성

    ```js
    // jest.setup.js
    import "@testing-library/jest-dom";
    ```

<br/>

#### 테스트 환경 추가 작업 : context 구문 사용

14. jest-plugin-context 설치 : <code>npm i jest-plugin-context</code>

<br/>

15. <code>jest.config.js</code> 파일에 다음 코드를 추가

    ```js
    module.exports = {
        setupFilesAfterEnv: [
            'jest-plugin-context/setup',  <-- 이거 추가
            './jest.setup',
        ],
        testEnvironment: 'jsdom',
    };
    ```

<br/>

16. <code>.eslintrc.js</code> 파일 수정

    ```js
    module.exports = {
      // ...
      globals: {
        context: "readonly",
      },
      // ...
    };
    ```
