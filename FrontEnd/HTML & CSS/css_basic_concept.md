# CSS의 소개와 기본 문법

<br/>

> 참고 자료 : 《<a href="https://github.com/SangYoonLee1231/TIL/blob/main/HTML%20%26%20CSS/html_basic_concept.md">HTML의 기본</a>》 페이지 참고

<br/>

### 목차

- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/HTML%20%26%20CSS/css_basic_concept.md#-css-%EC%86%8C%EA%B0%9C">CSS 소개</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/HTML%20%26%20CSS/css_basic_concept.md#html-%ED%8C%8C%EC%9D%BC%EC%97%90-css%EB%A5%BC-%EC%B6%94%EA%B0%80%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95">HTML 파일에 CSS를 추가하는 방법</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/HTML%20%26%20CSS/css_basic_concept.md#css-%ED%8C%8C%EC%9D%BC%EC%97%90-css%EB%A5%BC-%EC%B6%94%EA%B0%80%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95">CSS 파일에 CSS를 추가하는 방법</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/HTML%20%26%20CSS/css_basic_concept.md#css-%EA%B8%B0%EB%B3%B8-%EB%AC%B8%EB%B2%95">CSS 기본 문법</a>

<br/><br/>

## 🗨 CSS 소개

- ✨ <strong>CSS (Cascading Style Sheet) 는 브라우저에게 웹 사이트가 어떻게 보여야 하는지 알려주는 언어이다.</strong>

- CSS는 HTML과 함께 쓴다.

<br/>

- CSS는 <strong>선택자(Selector)</strong>를 통해 HTML 태그를 가리키고, 디자인 효과(스타일)를 부여하는 역할을 한다.

- CSS = <strong>Cascading Style Sheet</strong> : 위에서 아래로 코드를 읽는다.

  ☞ 같은 속성 코드가 중복 작성 시, <strong>제일 마지막 줄이 브라우저에 반영</strong>

<br/><br/>

## HTML 파일에 CSS를 추가하는 방법

- 【<strong>inline CSS</strong>】 html 문서의 <code>\<style></code>태그 사이에 css 코드를 <strong>직접 작성</strong>한다.

  (<code>\<style></code>태그는 <code>\<head></code>태그 사이에 작성한다.)

  ```html
  <head>
    <style>
      /* 이 곳에 CSS 코드를 작성 */
    </style>
  </head>
  ```

<br/>

- 【<strong>external CSS</strong>】 css 파일을 <strong>따로 생성</strong>한 후, html 문서에서 <code>\<link></code>태그를 이용하여 html 파일과 css 파일을 서로 연결한다.

  (더 좋은 방법)

  ```html
  /* link 태그 속성 작성법 */
  <head>
    <link
      href="./styles.css (css 파일 이름)"
      rel="stylesheet"
      type="text/css"
    />
  </head>
  ```

  - <strong><code>link</code></strong> : link 태그로 사용할 css 파일을 링크해준다.

  - <strong><code>href</code></strong> : href 속성에 css 파일 경로를 작성한다.

  - <strong><code>type</code></strong> : link 태그로 연결되는 파일이 어떤 것인지 알려준다. 여기서 css 파일을 연결하므로 type 값은 항상 <code>text/css</code>이다.

  - <strong><code>rel</code></strong> : rel은 HTML 파일과 CSS 파일과의 관계를 설명하는 속성이다. css 파일을 링크할 때는 항상 <code>stylesheet</code> 값을 대입해준다.

<br/><br/>

## CSS 파일에 CSS를 추가하는 방법

- <code>import</code>를 이용한다.

  ```css
  /* style.css */

  @import "reset.css";
  ```

<br/>

- CSS 파일에 CSS를 추가하는 것이 HTML 파일에 CSS를 추가하는 것보다 더 낫다.

<br/><br/>

## CSS 기본 문법

- 용어 정리

  - <strong>선택자(Selector), 속성 (속성이름, 속성값)</strong>

    ```css
    ↙ 선택자 (Selector)
    h1 {
        font-style: italic;  ← 선언 (Declaration)
            ↑          ↑
        속성 이름   속성 값
        (Property)  (Value)
    }
    ```

<br/>

- 속성 이름은 띄어쓰기를 해선 안 된다. (font-style처럼 '-'를 이용하여 띄어쓰기 표시)

- 각 줄은 세미콜론(';')으로 끝나야 한다.

- 속성 값(Value)엔 해당 속성(Property)에 맞는 값을 넣어주어야 한다.

<br/>

- 역시 모든 속성을 외우려 하지 말고 모르면 구글링하면 된다는 마인드로.

<br/><br/>

> 참고1 : 선택자 <code>\*</code>는 모든 요소를 가리킨다.

```css
* {
  border: 1px dashed black;
}
```

<br/>

> 참고2 : <code>border-radius</code> 속성에 50% 속성값을 주면 경계선은 원모양이 된다.

```css
* {
  border-radius: 50%;
}
```
