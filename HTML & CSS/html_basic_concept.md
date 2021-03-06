# HTML의 기본

<br/>

> 참고 자료 : 「<a href="https://nomadcoders.co/kokoa-clone" target="_blank">노마드 코더 - 코코아톡 클론코딩 강의</a>」, 「<a href="https://youtube.com/playlist?list=PLuHgQVnccGMAE4Sn_SYvMw5-qEADJcU-X">생활코딩 - 웹 애플리케이션 만들기</a>」, 학부 수업 자료

<br/><br/>

## 🗨 HTML 소개

- 웹사이트는 보통 3개의 언어로 구성되어 있다. - <strong>HTML, CSS, JavaScript</strong>

- 이 중 <strong>HTML</strong>은 웹사이트의 <strong>뼈대</strong>를 담당한다.

<br/>

- ✨ <strong>HTML</strong>은 인간의 언어를 이해하지 못하는 브라우저에게,

  <strong>웹사이트의 content(이미지, 제목, 사진, 사이드 바 등등..)가 어떻게 구성되어 있는지</strong> 설명할 때 쓰이는 언어이다.

  - "브라우저야 이건 <code>title</code>이고, 이건 날짜야. 이것은 <code>img</code>(이미지)이고 이 <code>img</code>는 따로 설명이 되어 있어."

- ✨ <strong>HTML</strong>의 모든 태그는 검색으로 찾아 쓸 수 있으니, 일일이 외우는 것보다 <strong>코드가 어떻게 작동하는 지를 이해하는 것이 중요하다.</strong>

<br/><br/>

## HTML 기본 문법

- HTML은 <strong>태그</strong>로 구성되어 있다.

- HTML 태그엔 두 종류가 있다. - <strong>『일반 태그』</strong> vs <strong>『Self-Closing 태그』</strong>

<br/>

```html
/* 일반 태그 작성법 */
<tag> content </tag>

/* Self-Closing 태그 작성법 */
<tag ... />
```

<br/>

- 일반 HTML 태그는 <strong>열고 반드시 닫아주어야</strong> 한다.

- 그리고 여는 태그(Start Tag)와 닫는 태그(End Tag)의 <strong>이름은 반드시 동일</strong>해야 한다.

- ✨ <strong>여는 태그(Start Tag)</strong>와 <strong>닫는 태그(End Tag)</strong> 사이에 <strong>내용(Content)</strong>을 작성하고, 태그와 내용은 함께 HTML의 한 <strong>요소(Element)</strong>를 이룬다.

- Self-Closing 태그로 구성된 요소를 Void 요소라고 한다.

<br/>

- 만일 HTML 코드를 잘못 입력하더라도 브라우저는 <strong>에러를 표시하지 않는다.</strong>

  따라서 올바른 위치에 올바른 태그를 사용하는 것이 정말 중요하다.

<br/><br/>

## HTML의 기본 구조

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Document</title>
  </head>
  <body>
    <h1>hello world!</h1>
  </body>
</html>
```

- <strong>\<!DOCTYPE html></strong> : 이 파일은 html임을 브라우저에게 알리는 코드

- <strong>\<html></strong>은 <strong>\<head></strong> 부분과 <strong>\<body></strong>부분으로 나뉜다.

- <strong>\<head></strong> : 사용자의 눈에 보이지 않는 웹사이트 환경을 설정하는 부분

  (데이터를 설명하는 메타 데이터를 삽입하는 영역)

- <strong>\<body></strong> : 사용자가 볼 수 있는 content를 작성하는 부분

<br/><br/>

## HTML 속성(attribute)

- <strong>속성(attribute)</strong> : HTML 태그에 추가하여 태그의 동작을 제어하도록 사용자가 지정하는 값

- HTML 태그의 속성은 태그 이름과 <strong>반드시 띄어쓴다</strong>.
- attribute에 값을 넣을 때, <strong>큰 따옴표("")</strong>를 사용하는 것이 좋다. (작은 따옴표(''), 백틱(``) 사용 자제)

<br/>

```html
/* 작성법 */
<tagname attrName="">좋은 개발자가 되고 싶다</tagname>

/* 실제 사용 예시 */
<div id="title">
  <a href="http://google.com" target="_blank">구글로 이동</a>
  <input disabled />
</div>
```

<br/>

- 태그와 속성은 대소문자를 구분하지 않는다.

- 일부 attribute는 모든 태그에 사용 가능하다. (예: id, class, style)

- 반대로 일부 attribute는 특정 태그만 사용 가능하다. (예: \<a href="">, \<img src="">, \<input type="">)

<br/>

- 다양한 태그의 attribute(속성)이 존재하나 역시 무작정 암기 X. <strong>사용법을 이해하고 필요할 때 검색해서 찾아 쓰자.</strong>

- HTML은 attribute와 결합할 때 강력해진다.

<br/><br/>

## 🧩 조각 지식

### <code>index.html</code>

- 대부분의 웹 서버가 디폴트로 <code>index.html</code>을 찾아보도록 설정되어 있다.

<br/>

### VS Code 단축키 꿀팁

- 해당줄을 복붙할때는 <strong>shift + alt + 아래(or 위)방향키</strong>를 누르면 된다.

- <code>div class="name"</code>은 <strong><code>div.name</code></strong>으로 자동완성 된다.

- <code>div id="id"</code>는 <strong><code>div#id</code></strong>하시면 자동완성 된다

- 주석 처리는 작성후 <strong>Ctrl + /</strong> 하면 되고
  여러 개를 동시에 만들고 싶으면
  ex. <code>div</code>를 10개 -> <strong><code>div\*10</code></strong>하면 된다.
