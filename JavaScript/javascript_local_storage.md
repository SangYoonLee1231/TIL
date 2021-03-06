# JavaScript - 로컬 스토리지 (Local Storage)

> 참고 자료 : <a href="https://nomadcoders.co/javascript-for-beginners">노마드 코더 - 바닐라 JS로 크롬 앱 만들기</a>

<br/>

### 목차

- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/JavaScript/javascript_local_storage.md#%EB%A1%9C%EC%BB%AC-%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80-local-storage">로컬 스토리지 (Local Storage)</a>
  - <a href="https://github.com/SangYoonLee1231/TIL/blob/main/JavaScript/javascript_local_storage.md#local-storage%EC%9D%98-%ED%95%A8%EC%88%98">Local Storage의 함수</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/JavaScript/javascript_local_storage.md#%EB%A1%9C%EC%BB%AC-%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80-local-storage-%ED%99%9C%EC%9A%A9%ED%95%98%EA%B8%B0">로컬 스토리지 (Local Storage) 활용하기</a>
  - <a href="https://github.com/SangYoonLee1231/TIL/blob/main/JavaScript/javascript_local_storage.md#local-storage%EC%97%90%EC%84%9C-%ED%8A%B9%EC%A0%95-%ED%95%AD%EB%AA%A9%EC%9D%98-%EC%A1%B4%EC%9E%AC-%EC%9C%A0%EB%AC%B4%EC%97%90-%EB%94%B0%EB%9D%BC-%EB%8B%A4%EB%A5%B8-%EB%8F%99%EC%9E%91%EC%9D%84-%EC%88%98%ED%96%89%ED%95%98%EB%8F%84%EB%A1%9D-%ED%95%98%EA%B8%B0">Local Storage에서 특정 항목의 존재 유무에 따라 다른 동작을 수행하도록 하기</a>
  - <a href="https://github.com/SangYoonLee1231/TIL/blob/main/JavaScript/javascript_local_storage.md#local-storage%EC%97%90-%EA%B0%9D%EC%B2%B4%ED%98%B9%EC%9D%80-%EB%B0%B0%EC%97%B4%EC%9D%84-%EC%A0%80%EC%9E%A5%ED%95%98%EA%B3%A0-%EC%9D%B4%EB%A5%BC-js%EB%A1%9C-%EB%B6%88%EB%9F%AC%EC%98%A4%EB%8A%94-%EB%B0%A9%EB%B2%95">Local Storage에 객체(혹은 배열)을 저장하고, 이를 JS로 불러오는 방법</a>

<br/><br/>

## 로컬 스토리지 (Local Storage)

- 브라우저가 value를 저장하도록 해주는 API

- 작은 미니 DB 같다.

<br/>

### Local Storage의 함수

- <code>setItem</code> : Local Storage에 항목 추가하기

  ```javascript
  localStorage.setItem("Key", "Value");
  ```

- <code>getItem</code> : Local Storage에서 항목 불러오기

  ```javascript
  localStorage.getItem("Key");
  ```

  ```
  "Value"
  ```

- <code>removeItem</code> : Local Storage에 있는 항목 제거하기

  ```javascript
  localStorage.removeItem("Key");
  ```

<br/>

## 로컬 스토리지 (Local Storage) 활용하기

### Local Storage에서 특정 항목의 존재 유무에 따라 다른 동작을 수행하도록 하기

- app.js

  ```javascript
  // Local Storage에 Key와 Value값 저장
  localStorage.setItem("Key", "Value");

  // Key에 해당하는 Value값 불러와 Value 변수에 저장
  const Value = localStorage.getItem("Key");

  // Value 변수값의 존재 유무에 따른 조건문
  if (Value === null) {
    // 특정 Key의 Value값이 없을 경우 해당 블록 실행
  } else {
    // 특정 Key의 Value값이 있을 경우 해당 블록 실행
  }
  ```

<br/><br/>

### Local Storage에 객체(혹은 배열)을 저장하고, 이를 JS로 불러오는 방법

- Local Storage에 객체(혹은 배열)을 저장할 땐, <a href="https://github.com/SangYoonLee1231/TIL/blob/main/JavaScript/javascript_piece_info.md#jsonstringify---%EB%AA%A8%EB%93%A0-%EA%B2%83%EC%9D%84-%EB%AC%B8%EC%9E%90%EC%97%B4%EB%A1%9C-%EB%B3%80%ED%99%98%EC%8B%9C%ED%82%A4%EB%8A%94-%ED%95%A8%EC%88%98"><code>JSON.stringify()</code></a>를 통해 저장할 객체를 문자열로 바꾸어 저장한다.

  ```javascript
  const numList = [1, 2, 3, 4, 5];

  localStorage.setItem("numberList", JSON.stringify(numList));
  ```

- Local Storage에 저장된 객체(혹은 배열)을 JS로 불러올 땐, <code>JSON.parse()</code>를 통해 다시 객체로 변환해준다.

  ```javascript
  JSON.parse(localStorage.getItem("numberList"));
  ```