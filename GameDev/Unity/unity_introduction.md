# 유니티 (Unity) 소개 및 설치

<br/>

> 참고 자료 : <a href="https://www.edwith.org/unity5_2015_001/lecture/4216?isDesc=false">유니티5 게임 개발 입문 (서형석 강사님 - 커넥츠제단)</a>

<br/>

## 유니티 소개 및 설치

- 요즘 국내 인디 게엠 혹은 3D 게임의 80프로 이상이 유니티를 쓴다.

- 유니티는 게임 외에도 여러 분야에서 활용된다.

<br/>

### 유니티를 선택하는 이유

- 배우고 사용하기 쉬운 편이다.

  - 소스가 차단되어 있고 별 기능이 보이지 않아 처음에 학습하기 쉽다.

- 가격이 저렴하다.

  - 거의 모든 기능이 풀린 상태로 무료이다.

- 멀티플랫폼 지원이 제일 강력하다.

  - 단, 결제 기능과 같은 다른 기능을 붙일 때는 플랫폼 별로 차이가 존재한다.

- 개발 속도가 빠르다.

  - 바로 구현하고 바로 확인 가능하다.

<br/>

### 그럼 유니티는 만능일까?

- 아니다.

- 잘 사용하지 못하면 효율을 내기 어렵다.

  - 그리고 C#을 쓰기 때문에 느리다.

- 유니티를 쓰기 전에 기본기를 익혀야 한다.

  - 수학, (물리), ...

<br/>

- 즉, <strong>프로그래머로서 기본 소양을 갖추고</strong> 유니티를 사용해야 한다.

<br/>

### 그래도 유니티는

- 전 세계 사용자들로부터 가장 많은 사랑을 받는 3D 엔진이다.

<br/>

### 유니티 설치

(생략)

<br/><br/>

## 유니티 기본 용어 정리 및 레이아웃 설정

### 기본 용어 정리

#### 어셋 (Asset)

- 엔진에서 사용되는 <strong>모든 자원(Resource)</strong>

  - 블록 파일, 3D 모델링 파일, 애니메이션, 코드 등등

<br/>

#### 게임 오브젝트 (GameObject)

- <strong>무엇이 게임 상에 존재하기 위한 최소한의 상태를 갖춘 것</strong>

  - ex) 어떤 오브젝트는 위치, 회전값, 크기값 등등을 가지고 있다.

  - 여기서 '위치, 회전값, 크기값 등등'을 컴퍼넌트(기능)라고 부른다.

- 모든 게임 오브젝트는 게임 공간 상에 존재하기 위해 Transform 컴퍼넌트를 지닌다.

<br/>

#### 컴퍼넌트 (Component)

- 게임 오브젝트에 구현된 각각의 <strong>기능</strong>

- 유니티에서 제공할 수도 있고, 사용자가 직접 구현헐 수도 있다.

- <strong>스크립트</strong>라고도 부른다.

<br/>

- ✨ 유니티에는 <strong>오브젝트</strong>가 있고, 여기에 <strong>여러 컴퍼넌트가 덕지덕지 붙어</strong> 하나의 자원이 된다.

<br/>

#### 프리팹 (Prefab)

- 게임 오브젝트에 구성되어 있는 기능들을 패키지화 시킨 어셋

- '책상의 부품을 조립하여 하나의 책상으로 만드는 것'과 같은 반복 작업을 효율화 시키기 위해, 한 번 구성해놓은 것을 하나의 패캐지로 묶어주는 단위

- 패캐지화한 프리팹은 필요할 때 세상에 꺼내 쓰면 된다.

<br/>

- 패캐지를 통해 세상에 꺼내진 모든 것들은 항상 이 원본 패캐지를 바라보고 있다.

- 즉, 원본이 바뀌면 바라보는 모든 것들도 같이 바뀐다.

- 하나를 꺼내서 수정하고 원본에 덮어 씌우면 모든 요소를 한 번에 수정할 수 있다.

- 만일 원본을 바꾸지 않고 어떤 하나만 바꿔서 쓰고 싶으면, 그 하나만 바꿔 쓰면 된다. (당장에는 원본에 영향을 끼치지 X)

  - 찜찜하면 그것이 원본을 바라보지 않도록 끊으면 된다.

<br/>

- 패캐지를 통해 세상에 꺼내진 모든 것들의 위치값이나 회전값은 각자 개인 고유의 값이므로 원본이 바뀌어도 달라지지 않는다.

<br/>

### 유니티 인터페이스

### 레이아웃 설정하기

- 우측 상단의 2 by 3, 4 split, .. 항목이 있는 요소를 통해 자신만의 레이아웃을 설정하고 이를 저장할 수 있다.

<br/><br/>

## 유니티 주요 View

<img src="img/unity_introduction1.png">

- 게임을 제작하는 과정은 영화를 촬영하는 과정과 비슷하다.

### Scene View

- 영화의 세트장에 비유. 게임의 '세트장'을 조작하는 화면 (게임 세상을 편집하기 위한 뷰)

- Scene View에서 게임 속 세상을 구성해야 실제 게임 및 어플리케이션 개발이 가능하다.

- Scene View에서 오브젝트를 자유롭게 조작할 수 있다. (오브젝트 배치, 회전, 크기 조절 등)

<br/>

### Game View

- 게임이 구성되고 최종적으로 보여지는 뷰

- 영화의 '카메라'에 비유. 게임의 '카메라'에 찍힌 화면

- 같은 세트장이라 하더라도 카메라의 위치나 구성에 따라 보이는 화면은 완전히 다르다.

- 보이는 것 뿐만 아니라, UI에서의 입력 처리도 할 수 있다.

  - 입력 : 마우스 클릭, 스파트폰 화면 터치 등등 (단, 스마트폰에서 듀얼 터치 입력은 따로 처리해야 한다)

<br/>

### Hierarchy View

- Scene View상에 배치된 수많은 오브젝트의 목록을 표시하는 리스트 뷰

- 우리가 '세트장'에 구성한 모든 요소에 대한 목록을 표현하고 관리한다.

- Scene View에서, 어떤 것을 새상으로 꺼내면 Hierarchy View에도 반드시 표시된다. 즉, Scene View와 Hierarchy View는 서로 링크로 연결되어 있다.

- 계층 뷰. 리스트 뷰라고 부르는 것이 옳은 표현이나 관리 구조가 계층 구조이므로 Hierarchy View라 부른다. (폴더로 관리)

- 계층 구조는 코드에서도 바꿀 수는 있다.

<br/>

### Project View

- 게임을 구성하는 다양한 Asset을 관리하기 위한 뷰

- 영화 세트장의 '창고'에 비유

- Project View에 표시된 Asset들을 우리는 세상에 꺼내놓는다.

- 유일하게 하드디스크에 연결된 뷰이다.

<br/>

### Inspector View

- 선택된 기능 또는 게임 오브젝트의 컴퍼넌트 내용을 보여주는 에디터 뷰

- 일종의 편집 창. 무언가의 설정을 바꾸는 뷰라고 이해하면 좋다.

- (예시) 어떤 오브젝트에 조명이라는 컴포넌트(기능)를 갖다 붙이면 조명이 된다. 이 때, 조명의 밝기나 색깔 등을 바꾸는 곳이 Inspector View이다.

- 프로그래밍 없이 여러 설정을 바꿀 수 있기 때문에 유니티의 개발 속도가 빠르다.

- Inspector View는 다양한 기능을 관리하므로 그 모습도 다양하다. 또한, 우리의 Need에 맞게 직정 수정해서 사용할 수도 있다.

- 에디터를 편집하는 기능을 익히고 싶으면 ngy 에셋의 코드를 분석하는 것을 권장한다.

<br/>

- Hierarchy View, Project View, Inspector View 세 개의 뷰는 붙여놓고 작업하는 것이 편하다.

<br/>
