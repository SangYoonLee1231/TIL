# 데이터 통신 소개 및 네트워크 기초

<br/>

> 참고 자료 : <a href="https://youtube.com/playlist?list=PL0d8NnikouEWcF1jJueLdjRIC4HsUlULi">네트워크 유튜브 강의 (따라하면서 배우는 IT)</a>, '데이터 통신' 학부 수업 내용 및 전공 서적 '데이터 통신' (Behrouz A. Forouzan 저 | 이재광, 김봉한 판역 | Mc Graw Hill 출판)

<br/><br/>

### 목차

- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Network/network_basic.md#%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%86%B5%EC%8B%A0-%EC%8B%9C%EC%8A%A4%ED%85%9C-%EC%86%8C%EA%B0%9C">데이터 통신 시스템 소개</a>

  - <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Network/network_basic.md#%ED%86%B5%EC%8B%A0-%EC%8B%9C%EC%8A%A4%ED%85%9C-%EA%B8%B0%EB%B3%B8-%ED%8A%B9%EC%84%B1">통신 시스템 기본 특성</a>
  - <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Network/network_basic.md#%ED%86%B5%EC%8B%A0-%EC%8B%9C%EC%8A%A4%ED%85%9C-%EA%B5%AC%EC%84%B1-%EC%9A%94%EC%86%8C">통신 시스템 구성 요소</a>
  - <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Network/network_basic.md#%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%91%9C%ED%98%84">데이터 표현</a>
  - <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Network/network_basic.md#%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A0%84%EC%86%A1-%EB%B0%A9%EC%8B%9D">데이터 전송 방식</a>

- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Network/network_basic.md#%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%EB%9E%80">네트워크란?</a>

  - <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Network/network_basic.md#%EC%9D%B8%ED%84%B0%EB%84%B7%EC%9D%B4%EB%9E%80">인터넷이란?</a>
  - <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Network/network_basic.md#%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%EC%9D%98-%EB%B6%84%EB%A5%98">네트워크의 분류</a>
  - <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Network/network_basic.md#%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC%EC%9D%98-%ED%86%B5%EC%8B%A0-%EB%B0%A9%EC%8B%9D">네트워크의 통신 방식</a>

- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Network/network_basic.md#%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%ED%94%84%EB%A1%9C%ED%86%A0%EC%BD%9C">네트워크 프로토콜</a>

- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Network/network_basic.md#%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EB%AA%A8%EB%8D%B8--tcp-osi-7-layer-%ED%8C%A8%ED%82%B7">네트워크 모델 : TCP, OSI 7 layer, 패킷</a>

- <a href="https://github.com/SangYoonLee1231/TIL/blob/main/Network/network_basic.md#%ED%8C%A8%ED%82%B7">패킷</a>
<!-- - <a href=""></a> -->

<br/><br/>

## 데이터 통신 시스템 소개

- 데이터 통신이란, 특정 형태의 전송 매체(전선 등)를 통해 두 장치 간에 데이터를 교환하는 것이다.

<br/>

### 통신 시스템 기본 특성

#### 효과적인 데이터 통신을 위해 데이터 통신 시스템은 아래의 4가지 기본 특성을 가진다.

- <strong>전달성 (Delivery)</strong> : 데이터를 정확한 목적지에 전달해야 함

- <strong>정확성 (Accuracy)</strong> : 데이터 정보를 정확하게 전달해야 함

- <strong>적시성 (Timeliness)</strong> : 정확한 타이밍에 (적시에) 데이터를 전송해야 함

- <strong>파형 난조 (Jitter)</strong> : 패킷들의 도착 시간이 조금씩 다름. 음성이나 동영상 패킷 전달 시 품질이 고르지 못하게 됨.

<br/>

### 통신 시스템 구성 요소

- <strong>메세지 (Message)</strong> : 통신의 대상이 되는 정보

- <strong>송신자 (Sender)</strong> : 메세지를 보내는 장치

- <strong>수신자 (Receiver)</strong> : 메세지를 받는 장치

- <strong>전송매체 (Medium)</strong> : 메세지를 전달하는 물리적 통로 (꼬임쌍선, 통축 케이블, 광섬유 케이블, 공기(무선 전송) 등)

- <strong>프로토콜 (Protocol)</strong> : 통신을 통제하는 규칙의 집합 (통신 규약)

<br/>

### 데이터 표현

#### **문자, 숫자, 영상, 오디오, 비디오**

- **유니코드 (Unicode)** : 32bit를 사용하여 전세계의 모든 문자와 부호를 나타낸 코드

<br/>

### 데이터 전송 방식

- **단방향 방식 (Simplex Mode)** : 통신이 일방통행으로 일어남

- **반이중 방식 (Half-Duplex Mode)** : 송수신 모두 가능하나, 무전기처럼 동시에는 할 수 없음

- **전이중 방식 (Full-Duplex Mode)** : 동시에 송수신 모두 가능

<br/><br/>

## 네트워크란?

- 통신망이다.

- 데이터를 서로 공유할 수 있도록 하는 디지털 전기 통신망의 하나이다.

- 전세계가 연결되어 있는 네트워크 망의 한 종류 : 인터넷

<br/>

### 인터넷이란?

- 여러 데이터를 주고 받을 수 있는 세상에서 가장 큰 네트워크 망이다.

- 네트워크 보단 작은 개념이다.

- 인터넷을 통해 가장 많이 이용하는 서비스 : 웹 서비스 (www)

<br/>

### 네트워크의 분류

#### 크기에 따른 분류

- **LAN (Local Area Network)**

  - 가까운 지역을 하나로 묶은 네트워크 통신망

  - 근거리 통신망

- **MAN (Metropolican Area Network)**

  - LAN보다 크고 WAN보다 작은 통신망

  - 분류가 모호하야 잘 쓰이지는 않는 개념

- **WAN (Wide Area Network)**

  - 멀리 떨어진 곳끼리 연결한 네트워크 통신망

  - 여러 개의 LAN 네트워크가 서로 연결되어 있는 것

<br/>

#### 연결 형태에 따른 분류

- **Star형 (성형)**

  - 중앙 장비에 모든 노드가 연결되어 있음

  - 중앙 장비가 고장나면 전부 먹통
  - LAN 대역을 만들 때 많이 사용

- **Mesh형 (망형)**

  - 모든 노드들이 서로서로 전부 연결되어 있음

  - 장비가 고장나도 어느 정도는 문제 없음
  - WAN 대역을 연결할 때 많이 사용

- **혼합형**

  - LAN + WAN

<br/>

### 네트워크의 통신 방식

- **유니 캐스트**

  - 내가 통신하고 싶은 특정 한 사용자하고만 통신하는 것

- **멀티 캐스트**

  - 특정한 다수와 통신하는 것

- **브로드 캐스트**

  - 같은 네트워크 대역에 있는 모든 사람들과 통신하는 것

<br/><br/>

## 네트워크 프로토콜

- **일종의 약속, 일종의 양식**

- 네트워크에서 노드와 노드가 통신할 때 어떤 노드가 어느 노드에게 어떤 데이터를 어떻게 보내는 지 작성하기 위한 양식

- 여러가지 프로토콜

  - 가까운 곳과 연락할 때 : **Ethernet 프로토콜**

    - (언어 : MAC 주소)

  - 멀리 있는 곳과 연락할 때 : **ICMP, IPv4, ARP**

    - (언어 : IP 주소)

  - 여러가지 프로그램으로 연락할 때 : **TCP, UDP**

    - (언어 : 포트 번호)

  - 인터넷 : **HTTP**

<br/>

- 여러 프로토콜을 함께 사용한다.

  - 프로토콜들이 합쳐진 모양 : **캡슐레이션, 패킷**

<br/><br/>

## 네트워크 모델 : TCP, OSI 7 layer, 패킷

- 네트워크 계층 모델 - TCP / IP 모델 (프로토콜 기반)

  - 5계층 : **응용**
  - 4계층 : **전송**
  - 3계층 : **네트워크**
  - 2계층 : **데이터 링크**
  - 1계층 : **물리**

- 네트워크 계층 모델 - OSI 7계층 (네트워크 표준 모델) (역할 기반)

  - 7계층 : 응용 - HTTP, SSH
  - 6계층 : 표현 - SMB
  - 5계층 : 세션 - NetBIOS
  - 4계층 : 전송 - TCP, UDP
  - 3계층 : 네트워크 - IP, ICMP, IGMP, ARP
  - 2계층 : 데이터 링크 - 이더넷, 토큰링
  - 1계층 : 물리 - 전선, 전파, 광섬유, 동축케이블

<br/><br/>

## 패킷

- 네트워크 상에서 전달되는 데이터를 통칭하는 말

- (데이터의 형식화 된) 블록

- 여러 프로토콜이 합쳐진 모양 (순서 존재)

<br/>

- 제어 정보 + 사용자 데이터 (페이로드)

- **헤더 + 페이로드** + (풋터)

<br/>

#### 패킷을 만드는 과정 : **인캡슐레이션** (캡슐화)

- 요청을 받고 패킷을 보낼 때 캡슐화 과정을 거침

- 상위 계층 → 하위 계층

- [1][2][3][4][데이터]

<br/>

#### 패킷을 확인하는 과정 : **디캡슐레이션**

- 패킷을 받을 때 이 패킷을 까보는 과정

- 하위 계층 → 상위 계층

- [1][2][3][4][데이터]

<br/>

- 각 계층에서 패킷들을 부르는 용어가 다 다르다

  - **세그먼트** = (OSI 기준)4계층의 PDU

    - [(4)TCP]+[데이터]

  - <strong>패킷 (다른 용어) or 데이터그램</strong> = 3계층의 PDU

    - [(3)IPv4]+[(4)TCP]+[데이터]

  - **프레임** = 2계층의 PDU

    - [(2)Ethernet]+[(3)IPv4]+[(4)TCP]+[데이터]

  - (PDU = Protocol Data Unit)

<br/>
