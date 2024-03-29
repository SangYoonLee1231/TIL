## Chapter 2. Web의 동작 원리 - 클라이언트와 서버의 만남

### 1. Web의 등장

#### Web의 등장

- 90년대 후반 퍼스널 컴퓨터 보급 시작 → 인터넷의 보급으로 이어지진 않음

- 2000년대 초반 초고속 인터넷망이 보급되기 시작

  - 그 전 PC 통신은 전화 통신을 활용하였다.

  - 서로 다른 사업자간 통신 불가능

  - 종량제로 과금 내는 방식 → 요금 폭탄 맞을 가능성

- WWW = World Wide Web

  - 세계를 널리 연결하는 망, 시공간 제약 X

  - 팀 버너스 리께서 개발

- PC 통신 vs Web

  - PC 통신 : 페쇄적, 저속, 전화선/모뎀

  - Web : 개방적, 고속, 광랜(FTTH)

<br/>

#### Web의 역사

- **Web 1.0 (1990년대 후반 ~ 2000년대)**

  - 초고속 인터넷이 보급되던 시절

  - 어느 누구나 프로그램을 대중에 공개할 수 있는 시대 도래
  - 닷컴 붐으로 다양한 웹 서비스가 등장
  - 하지만 일부 서비스만 살아남음 (닷컴 버블이 붕괴)

- **Web 2.0 (2010년대 ~ 현재)**

  - 알방향적으로 정보를 제공받던 사용자가 이제 직접 정보를 생산하고 공유하는 시대

  - 누구나 정보에 쉽게 접근할 수 있다는 가치 아래에서 웹 생태계가 폭발적으로 발전
  - ex) 위키피디아, 블로그 등
  - 검증되지 않는 정보들도 많음 → 사용자의 분별이 필요함
  - **결정적 사건** → 스마트폰의 시대 시작 (리얼 타임 시대)
  - SNS, 영상통화 등장

- **Web 3.0 (현재 ~ )**

  - 현재는 과도기

- 블록체인 기술

  - 데이터를 투명하게 공개해야 한다는 것을 가장 큰 가치로 둠 → 이로 인해 나온 기술

  - 가상 화폐

<br/>

### 2. 클라이언트와 서버

- 웹 브라우저 : 크롬 (점유율 1위), 사파리 등

- 사용자가 인터넷 상의 정보를 활용하기 위해선 브라우저의 도움을 반드시 받아야 한다.

- 클라이언트 (client) : 브라우저를 통해 요청을 보내는 주체

- 서버 (server) : 클라이언트의 요청을 처리해 응답하는 주체

<br/>

### 3~4. HTTP와 URL

- 프로토콜 (Protocol) : 서로 통신할 때 필요한 (일정한) 규칙 (여권에 비유)

- **HTTP** : HyperText를 통해 이동하려는 페이지의 정보를 요청하고, 이를 응답받는 규칙

  - HyperText Transfer Protocol

  - (HyperText : 다른 페이지로 이동할 수 있는 링크)

- **클라이언트와 서버는 HTTP라는 규칙을 통해 서로 소통한다.**

<br/>

- **URL** : 인터넷 상에 위치해있는 각종 자원들의 주소 체계를 가리키는 말 (Uniform Resource Locator)

  - 서버에 저장된 웹 페이지 및 자원들은 모두 자신이 위치한 URL을 가지고 있다.

- URL 분석 - 예시 : `https://www.google.com/search?q=techit`

  - `https://` : 프로토콜 (통신 규칙)

  - `www.google.com` : 호스트 (서버의 주소)

  - `/search` : 경로 (웹서버에 자원의 위치를 찾아 들어감)

  - `q=techit` : 쿼리 문자열 (Query String)

<br/>

### 5. 쿠키와 세션

- **쿠키** : 서버에서 클라이언트로 보내져서 브라우저에 저장되는 아주 작은 크기의 데이터

  - 키/값 구조, 유효기간 있음

  - 클리아언트, 서버의 통신은 Stateless(통신 내용을 기억하지 못함)이기 때문에 통신 내용을 어딘가에 저장해두어야 한다.

  - 페이지를 이동해도 로그인이 풀리지 않는 이유가 바로 클라이언트에 쿠기가 존재하기 때문

  - 민감한 데이터는 쿠키에 담으면 안된다. (보안에 유의)

- **세션** : 쿠키의 한계점을 보완하기 위해 나온 개념

  - 쿠키에 담길 내용을 서버의 세션 저장소에 저장하고, 처음 로그인 시 클라이언트에는 Session ID만을 보내준다.

  - 클라이언트에서 Session ID를 통해 다시 로그인 요청을 서버에 보내면, 서버는 해당 Session ID를 기반으로 세션 저장소에서 상태 데이터를 찾아 보내준다.

  - 민감한 데이터가 노출될 수 있는 쿠기의 단점을 보완

<br/>

### 6~9. IP, Port 그리고 DNS

#### **네트워크** : 두 대 이상의 컴퓨터가 서로 연결되어 통신할 수 있게된 체계, 통신망

- 어떨게 데이터가 오고 가는지를 이해하는 것이 네트워크의 핵심이다.

- 네트워크의 구성 요소인 개별 컴퓨터를 **Host**라 부른다.

- 많은 컴퓨터를 연결하여 통신이 가능하려면 매개체가 필요한데, 이를 **Switch**라 한다.

- Switch는 다른 네트워크에 접근할 수 없다.

- **Router**는 서로 다른 네트워크 간에 통신을 할 수 있도록 해준다. (실생활에서는 공유기라 많이 부름)

- 전 세계에 퍼져있는 거대 네트워크 망을 <strong>인터넷(Internet)</strong>이라 부른다.

<br/>

#### **IP** (Internet Protocol) : 컴퓨터 간 데이터를 주고받는 네트워크 계층의 규약

- 네트워크 계층의 규약에 따라 데이터 전달에 필요한 목적지 컴퓨터의 정보가 반드시 필요하다.

- **IP 주소** : 네트워크에서 컴퓨터가 부여받는 고유한 주소 (IPv4 vs IPv6)

  - `0.0.0.0` ~ `255.255.255.255` (IPv4 기준)

- **공인 IP vs 사설 IP**

  - ISP (Internet Service Provider) : 인터넷 서비스 제공자 (예: SK broadband, kt, LG U+)

  - <strong>공인 IP (Public IP)</strong> : 전체 인터넷 망에서 고유하게 식별 가능한 주소

    - ISP는 컴퓨터나 공유기에 공인 IP를 할당

    - IPv4 체계에서 자원 부족

  - <strong>사설 IP (Private IP)</strong>

    - 가정의 LAN과 같은 네트워크에서 할당되는 주소

    - 컴퓨터에서 조회되는 IP

    - 하나의 공인 IP에서 수많은 사설 IP 할당 가능

- <strong>특수한 IP 주소 : `127.0.0.1`</strong>

  - 컴퓨터에서 자기 자신을 가리키기 위해 약속된 IP 주소

  - 호스트 명 : `localhost`

<br/>

#### Port : 하나의 컴퓨터에서 실행되는 다양한 서비스(앱)를 구분하는 역할

- IP 주소만으로는 수행되는 다양한 서비스 중 어떤 서비스로 데이터를 보내야 할지 알 수 없다.

- 포트 번호 대포적 예시

  - HTTP : 80

  - HTTPS : 443

  - SMTP : 25

  - FTP : 21

- 웹 개발을 할 때 접근하려는 서비스의 목적지 포트를 정확하게 설정하는 것이 중요하다.

<br/>

#### DNS (Domain Name Server) : URL(도메인 네임)을 해석하여 IP 주소로 반환하는 서버

- 동작 과정

  - 클리이언트는 DNS 서버 도메인 네임을 보낸다.

  - DNS 서버는 클라이언트에게 해당 도메인 네임에 해당하는 IP 주소를 반환한다.

  - 클라이언트는 이 IP 주소를 바탕으로 원하는 웹 사이트에 찾아 들어간다.

- 국가, 기업 등이 운영한다.

- 전세계 DNS는 연결되어 있다.

- 장애 발생 시 막대한 피해로 이어질 수 있다.

<br/>
