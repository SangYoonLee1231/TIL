# CSS - Display 속성 : Block과 Inline

<br/>

> 참고 자료 : 《<a href="https://github.com/SangYoonLee1231/TIL/blob/main/HTML%20%26%20CSS/html_basic_concept.md">HTML의 기본</a>》 페이지 참고

<br/>

- CSS의 <code>display</code> 속성은 화면에 여러 요소들을 어떻게 배치할 지 결정한다.

- 웹페이지의 레이아웃(layout)을 결정한다고 해도 무방하다.

```css
div {
  display: block;
}
```

<br/>

## ✨ Block VS Inline

- <strong>Block</strong>

  - <code>block</code> 태그 옆엔 <strong>다른 요소가 올 수 없다.</strong>

  - <code>block</code>은 <strong>높이</strong>(<code>height</code>)와 <strong>너비</strong>(<code>width</code>)를 가진다.

  - <code>block</code>은 <strong>Box</strong>이고, 여백과 관련된 3가지 중요한 특징을 가진다.

    : <code>margin</code>, <code>border</code>, <code>padding</code>

    (<code>inline</code>도 가지고 있는 특징이다. 상하 margin만 제외하고)

  - Block 속성을 갖는 HTML 요소 : <code>\<div></code>, <code>\<p></code>, <code>\<address></code>, ..

  - Block 속성을 갖는 HTML 요소는 <code>width</code> 속성을 부여하지 않으면 기본적으로 화면 크기의 좌우 끝 전체를 차지한다.

<br/>

- <strong>Inline</strong>

  - <code>inline</code> 태그 옆에 <strong>다른 요소가 올 수 있다.</strong>

  - <code>inline</code>은 ✨<strong>높이</strong>(<code>height</code>)와 <strong>너비</strong>(<code>width</code>)를 <strong>가질 수 없다.</strong>

    - 따라서 ✨<strong>위, 아래에 </strong><code>margin</code><strong>을 가지지 않는다.</strong>

      (가지도록 하려면 <code>display</code> 속성을 <code>inline-block</code>으로 바꾸어야 한다)

  - Inline 속성을 갖는 HTML 요소 : <code>\<span></code>, <code>\<a></code>, <code>\<img></code>, ..

<br/>

## 여백과 관련된 속성 1 : margin

- <code>margin</code>은 <strong>요소의 경계(border)의 바깥에 있는 영역</strong>이다.

- <code>block</code>과 <code>inline</code> 요소 모두 가지고 있는 특징이나, <code>inline</code>은 <strong>상하에</strong> <code>margin</code><strong>을 가지지 않는다.</strong>

  ```css
  div {
    margin: 20px; /* 전방향 */
    margin: 20px 15px; /* 상하 좌우 */
    margin: 20px 5px 15px 10px; /* 상 우 하 좌 */

    margin-top: 20px;
    margin-bottom: 15px;
    margin-right: 5px;
    margin-left: 10px;
  }
  ```

<br/>

- <code>margin</code>에 <strong><code>auto</code></strong> 값을 주면 요소를 해당 방향의 중앙에 배치시킬 수 있다.

  ```css
  .center {
    margin: 10px auto;
  }
  /* 요소를 좌우, 즉 가로 방향 기준으로 중앙에 배치한다. */
  ```

<br/>

- <strong>user agent stylesheet</strong> :

  브라우저가 기본적으로 부여한 style 속성  
  ex) <code>body { margin : 8px; }</code>

  - 이를 없에려면 <strong><a href="https://github.com/SangYoonLee1231/TIL/blob/main/HTML%20%26%20CSS/css_piece_info.md#reset-css">Reset CSS</a></strong>를 적용해주면 된다.

- <strong>Collasping Margins</strong> :

  box 요소의 경계가 부모 box 요소의 경계와 일치하면, 이 두 <code>margin</code>이 하나로 취급되는 현상

  - 위, 아래에서만 일어난다.

<br/>

## 여백과 관련된 속성 2 : padding

- <code>padding</code>은 <strong>box의 경계(border)로부터 안쪽에 있는 영역</strong>이다.

- <code>block</code>과 <code>inline</code> 요소 모두 가지고 있는 특징이다.

```css
div {
  padding: 20px; /* 전방향 */
  padding: 20px 15px; /* 상하 좌우 */
  padding: 20px 5px 15px 10px; /* 상 우 하 좌 */

  padding-top: 20px;
  padding-bottom: 15px;
  padding-right: 5px;
  padding-left: 10px;

  /* 규칙은 margin과 동일하다. */
}
```

<br/>

## 여백과 관련된 속성 3 : border

- <code>border</code>은 말 그대로 박스의 '<strong>경계</strong>'이다.

- <code>block</code>과 <code>inline</code> 요소 모두 가지고 있는 특징이다.

- <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-style">border 스타일 종류 확인하기 (MDN 문서)</a>

  ```css
  div {
    border: 1px solid black;
    /* border: 너비 스타일 색깔 */
  }
  span {
    border: 2px dotted blue;
  }
  ```

<br/>

- <code>border</code>은 다양한 속성값이 존재하나 대부분 이쁘지 않으므로 거의 한 종류만 쓴다.

<br/>

## 또 하나의 Display 속성 : Inline-block

- <code>inline-block</code>은 높이와 너비를 가지는 동시에, 바로 옆에 다른 요소가 올 수 있는 <code>display</code> 속성이다.

  ```css
  div {
    display: inline-block;
  }
  ```

<br/>

- 그러나 <strong>많은 문제점</strong>을 가지고 있으므로 사용을 지양한다.

  - 【문제점 1】 정해진 형식이 없고, <code>inline-block</code> 요소들 사이에 의미불명한 빈 공간이 생긴다.

  - 【문제점 2】 <strong>반응형 디자인(Responsive Design)을 자원하지 않는다.</strong>

    - 창 크기가 달라지면 영향을 받는다.
