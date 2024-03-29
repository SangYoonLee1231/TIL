# 개발자 도구

> 작성한 블로그 포스트를 바탕으로 정리하였습니다.

<br/>

### 목차

- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Etc/DevTools.md#%EA%B0%9C%EB%B0%9C%EC%9E%90-%EB%8F%84%EA%B5%AC-devtool-%EB%9E%80">개발자 도구 (DevTool) 란?</a>
- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Etc/DevTools.md#%EA%B0%81-%ED%8C%A8%EB%84%90%EC%9D%98-%EA%B8%B0%EB%8A%A5">각 패널의 기능</a>

  - <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Etc/DevTools.md#elements-%ED%8C%A8%EB%84%90">Elements 패널</a>
  - <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Etc/DevTools.md#console-%ED%8C%A8%EB%84%90">Console 패널</a>
  - <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Etc/DevTools.md#network-%ED%8C%A8%EB%84%90">Network 패널</a>
  - <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Etc/DevTools.md#application-%ED%8C%A8%EB%84%90">Application 패널</a>

<br/><br/>

## 개발자 도구 (DevTool) 란?

- 개발자들이 홈페이지를 수정하고, 발생한 문제의 원인을 쉽게 파악하기 위해 브라우저에서 제공하는 도구이다.

- 윈도우나 맥에서 F12를 클릭하면 열 수 있으며, 주로 개발자 도구를 열어놓고 작업을 하는 경우가 굉장히 많기 때문에, 개발자 도구의 사용법을 잘 아는 것은 중요하다.

<br/>

- 개발자 도구에는 여러 개의 패널이 존재한다.

  이 각 패널의 기능을 잘 숙지하여 적절한 상황에 알맞은 패널을 활용하자.

<br/><br/>

## 각 패널의 기능

## Elements 패널

<img alt="dev-tool_element" src="img/dev-tool_element.png">

- HTML과 CSS 코드를 분석하고 실시간으로 이를 수정할 수 있는 패널이다. 사이트의 구조를 파악하는 데 용이하다.

 <br/>

- (CSS 코드를 확인할 수 있는) Styles 부분의 상단부터 CSS 속성이 우선적으로 적용되는 것을 표시한다고 보면 된다.

- 만일 하나의 요소에 동일한 스타일 속성이 부여되었다면, 더 상단에 표시된 속성이 요소에 적용된 것이다.

- 하단애 적힌 속성은 이렇게 중간에 줄이 그어진 상태로 표시될 것이다.

<br/>

### <code>user agent stylesheet</code>

- 브라우저에서 기본적으로 부여되는 스타일 속성을 말한다.

  - 하나의 예시로 여러 inline-block 요소들의 사이에 margin이 자동으로 부여되는 것을 들 수 있다.

- 브라우저마다 기본적으로 설정된 user agent stylesheet가 다르기 때문에, 보통 <a href="https://github.com/SangYoonLee1231/TIL/blob/main/HTML%20%26%20CSS/css_piece_info.md#reset-css"><code>reset.css</code></a> 혹은 <code>normalize.css</code>를 통해 기본 스타일을 모두 초기화 한 후 작업을 시작한다고 한다.

<br/><br/>

## Console 패널

<img alt="dev-tool_console" src="img/dev-tool_console.png">

- 자바스크립트를 실시간 환경에서 실행할 수 있는 환경을 제공해주는 패널이다.

- 브라우저에서 스크립트를 입력할 일이 생길 때 보통 다른 외부 도구(VS Code 등)를 활용하기보다, 개발자 도구의 Console 패널을 열어 코드를 입력한다고 한다.

#### 꿀팁

- [Enter] + [Shift]를 키보드에서 동시에 누르면 다음 줄에서 코드를 이어 작성할 수 있다.

- 콘솔 창의 모든 로그를 지우고 싶으면 console.clear()를 입력하면 된다.

- 새로고침을 해도 현재 입력한 로그를 유지하고 싶다면 [설정(톱니바퀴)] → [로그 보존]을 체크해주자.

- 콘솔 창에서 경고나 오류 표시를 보지 않도록 하려면 [필터] 오른쪽 영역의 [기본 수준 ▾]을 클릭하고 [경고]와 [오류]를 체크 헤제 해주면 된다.

- 만일 다른 패널에서 콘솔 창을 열고 싶다면, 다시 콘솔 패널로 돌아가지 말고 그 자리에서 [ESC] 버튼을 누르자.

  그럼 개발자 도구 하단에 콘솔 창이 나타날 것이다.

<br/><br/>

## Network 패널

<img alt="dev-tool_network" src="img/dev-tool_network.png">

- HTTP 네트워크의 통신을 확인할 수 있는 패널이다.

- 웹페이지에 포함된 모든 리소스들의 통신 과정과 그 정보들을 확인할 수 있으며, 오류가 발생 시 그 원인과 해결책을 찾을 수 있다.

- 프론트엔드와 백엔드가 서로 데이터 통신 시 오류는 없는지 확인하고자 할 때 가장 많이 열어보는 창이라 한다.

  (개발자들 사이에서 '이백오케이'라는 은어가 있는데, 서버와의 통신이 원할하게 잘 되었다는 의미라 한다.)

<br/><br/>

## Application 패널

<img alt="dev-tool_application" src="img/dev-tool_application.png">

- 브라우저의 저장소 기능을 담당하는 패널이다.

<br/>

### 저장소 종류

- <strong>Storage</strong> : 브라우저의 저장소. 쿠키의 단점을 보완해서 만들어졌기에 보안이 우수하다.
- <strong>Local Storage</strong> : 데이터를 영구적으로 저장할 수 있는 공간이다. 용량 또한 10MB로 크다. (key-value 형태의 객체로 데이터를 저장한다.)
- <strong>Sesson Storage</strong> : 윈도우나 브라우저 탭이 닫힐 경우 데이터가 사라지는 일회성용 데이터 공간이다.
  (key-value 형태의 객체로 데이터를 저장한다.)
- <strong>Cookie</strong> : 스토리지 개념이 도입되기 전 저장소로 사용되었던 공간이다. 지속시간을 설정할 수 있다. 다만 문자열 데이터만 저장할 수 있으며, 용량도 4KB로 작다.
