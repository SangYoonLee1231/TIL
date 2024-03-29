# CSS - Position

<br/>

> 참고 자료 : 《<a href="https://github.com/SangYoonLee1231/TIL/blob/main/HTML%20%26%20CSS/html_basic_concept.md">HTML의 기본</a>》 페이지 참고

<br/>

- CSS의 <code>position</code> 속성은 HTML 요소의 위치 설정 방식을 결정한다.

<br/><br/>

## Position 속성 1 : Fixed

- <code>fixed</code> 요소는, <strong>스크롤을 내려도 계속 처음 그 자리에 위치</strong>한다.

- <code>top</code>, <code>bottom</code>, <code>left</code>, <code>right</code> 속성 중 하나라도 수정 시, 해당 요소는 <strong>초기 위치가 무시</strong>되고, <strong>앞 쪽의 레이어로 넘어간다</strong>.

```css
div {
  position: fixed;
  top: 20px;
  right: 15px;
}
```

<br/><br/>

## Position 속성 2 : Static

- <code>static</code> 요소는 <strong>Default(초기)값</strong>이다.

- 요소의 위치를 지정하지 않는다.

```css
div {
  position: static;
}
```

<br/><br/>

## Position 속성 3 : Relative

- <code>relative</code> 요소는, <strong>처음 위치하는 곳을 기준</strong>으로 <code>top</code>, <code>bottom</code>, <code>left</code>, <code>right</code> 속성의 값만큼 위치를 (미세하게) 이동한다.

```css
div {
  position: relative;
  top: 10px;
  right: 20px;
  /* 처음 위치를 기준으로 위로 10px, 오른쪽으로 20px 이동 */
}
```

<br/><br/>

## Position 속성 4 : Absolute

- ✨ <code>absolute</code> 요소는, <strong>가장 가까운</strong> <code>relative</code> <strong>부모의 영역</strong>을 기준으로 <code>top</code>, <code>bottom</code>, <code>left</code>, <code>right</code> 속성을 통해 요소를 배치한다.

  - 이때, <code>relative</code>처럼 요소를 (미세하게) 이동하는 것이 아니라,

    부모 요소의 영역 안에서, 각 방향의 맨 끝부터 <code>top</code>, <code>bottom</code>, <code>left</code>, <code>right</code> 속성값만큼 떨어진 곳에 요소를 배치하는 것이다.

<br/>

- ✨ 만일 부모 중에 <code>relative</code> <strong>요소가 없으면</strong>, <code>absoulte</code> 요소는 <code>body</code><strong>를 기준</strong>으로 삼는다.

  - (부모 중에 position이 <code>relative</code>, <code>fixed</code>, <code>absolute</code>인 요소가 하나라도 있으면 그 부모가 기준이 된다)

<br/>

- 코드 예시

  ```css
  div {
    width: 300px;
    height: 300px;
    background-color: wheat;

    position: relative;
  }
  div > div {
    width: 100px;
    height: 100px;
    background-color: teal;

    position: absolute;
    bottom: 10px;
    right: 20px;
    /* 가장 가까운 relative 부모(div)의 영역을 기준으로, 맨 아래에서 10px, 맨 우측에서 20px 떨어진 곳에 배치 */
  }
  ```

<br/>

- 이 때, 해당 위치에 다른 요소가 있을 경우, 뒤로 밀리지 않고 <strong>덮어쓰게 된다.</strong>

<br/>

- 어떤 Block 요소가 <code>absolute</code> 값을 갖게 되면, 크기를 지정하지 않아도 내용의 크기만큼만이 요소의 크기가 된다.

<br/>

### (의문점)

```css
div {
    background-color: wheat;
    width: 300px;
    height: 300px;

    position: relative;
    top: 0px; ✔
}
div > div {
    background-color: teal;
    height: 100px;
    width: 100px;

    position: absolute;
    bottom: 10px; ✔
    left: 20px;
}
```

    부모 relative의 속성에 top: 0px를 주면, 자식 absolute에서 bottom: 10px가 제대로 동작하지 않는다. 그 이유는 뭘까..
