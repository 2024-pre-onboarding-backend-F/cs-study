## 4주차 주제 : 네트워크

### 🎨 공통 질문

1. **OSI 7 Layer의 각 계층에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

OSI 7 Layer은 네트워크에서 통신이 일어나는 과정을 7단계로 나눈 것입니다.

1계층은 물리 계층으로 데이터를 전기 신호로 바꾸어주는 계층입니다.

2계층은 데이터링크 계층으로 데이터의 물리적인 전송과 에러 검출, 흐름 제어를 담당하는 계층입니다.

3계층은 네트워크 계층으로 데이터를 목적지까지 가장 안전하고 빠르게 전달하기 위한 계층입니다.

4계층은 전송 계층으로 최종 수신 프로세스로 데이터의 전송을 담당하는 계층입니다.

5계층은 세션 계층으로 컴퓨터끼리 통신을 하기 위해 세션을 만드는 계층입니다.

6계층은 표현 계층으로 데이터의 형식(Format)을 정의하는 계층입니다.

7계층은 응용 계층으로 사용자에게 통신을 위한 서비스를 제공하는 계층입니다.
</details>

<details>
  <summary>정은경</summary>
  OSI 7계층은 네트워크 통신을 단계적으로 나눈 모델입니다.

  1계층은 물리계층으로 실제 데이터를 전송하는 하드웨어적 계층으로, 전기 신호나 광 신호를 매개로 데이터를 전송합니다.

  2계층은 데이터 링크 계층으로 물리계층에서 전달받은 데이터의 오류 검출, 수정, 흐름 제어 등을 담당하며 프레임 단위로 통신합니다.

  3계층은 네트워크 계층으로 데이터를 목적까지 전달하기 위해 경로를 설정하고 라우팅을 담당합니다.

  4계층은 전송 계층으로 데이터의 신뢰성 있는 전송을 보장하며, TCP/UDP를 통해 데이터 세그먼트를 관리합니다. 

  5계층은 세션 계층으로 통신 세션을 관리하고 연결을 유지하거나 동기화를 담당합니다.

  6계층은 표현 계층으로 데이터 포맷은 변환하고 암호화 및 압축 같은 작업을 수행합니다.

  7계층은 응용 계층으로 사용자와 가장 가까운 계층으로, 애플리케이션에서 사용하는 네트워크 서비스입니다.
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

2. **TCP Connection 시 3-way handshaking에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

TCP는 연결 지향적 프로토콜로, 장치들 사이에 논리적인 접속을 성립하기 위해 연결을 설정해 신뢰성을 보장하는 연결형 서비스를 말합니다. TCP는 3-way handshaking 과정을 통해 연결을 설정합니다.

이때 3-way handshaking이란 발신지와 수신지 사이에 논리적인 접속(세션)을 성립하는 과정을 의미합니다.

과정을 간단히 설명하면 먼저 Open한 클라이언트가 SYN을 보내고 SYN_SENT 상태로 대기하면 서버는 SYN-RECEIVED 상태로 바꾸고 SYN과 응답 ACK을 보냅니다. 
SYN과 응답 ACK를 받은 클라이언트는 ESTABLISHED 상태로 변경하고 서버에게 응답 ACK을 보내면, 응답 ACK를 받은 서버는 ESTABLISHED 상태로 변경합니다.
</details>

<details>
  <summary>정은경</summary>
  TCP 연결을 설정하기 위한 3-way handshaking은 연결 시작을 의미합니다.

  이 과정은 클라이언트가 서버에 연결 요청을 보내는 SYN, 서버가 요청을 수락하며 응답과 함께 자신의 연결 요청을 보내는 SYN-ACK, 클라이언트가 서버의 요청을 수락하며 응답을 보내는 ACK로 이루어져 있습니다. 이 과정을 통해 양측이 서로 인식하고 데이터 전송을 준비합니다.
  
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

3. **TCP와 UDP의 차이에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

TCP는 연결형 서비스로 3-way handshaking 과정을 통해 연결을 설정하기 때문에 높은 신뢰성을 보장하지만 속도가 비교적 느리다는 단점이 있습니다.

UDP는 비연결형 서비스로 3-way handshaking을 사용하지 않기 때문에 신뢰성이 떨어지는 단점이 있지만 데이터 수신 여부를 확인하지 않기 때문에 속도가 빠르다는 장점이 있습니다.
</details>

<details>
  <summary>정은경</summary>
  TCP는 연결 지향형 방식으로 데이터 전달을 보장하고 손실 시 재전송해주어 신뢰성을 보장합니다. 다만, 속도가 UDP에 비해 상대적으로 느립니다. 데이터의 순서를 보장하기에 HTTP, 이메일 등에 주로 사용됩니다.

  UDP는 비연결형 방식으로 신뢰성을 보장하지 않습니다. 하지만 TCP에 비해 상대적으로 속도가 빠릅니다. 데이터의 순서를 보장하지 않기에 스트리밍, 게임 서비스에 주로 사용됩니다.
  
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

4. **HTTP Method에는 어떤 것들이 있는지 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

HTTP Method는 클라이언트가 서버에게 사용자 요청의 목적을 알리는 수단으로, 종류에는 GET, POST, PUT, PATCH, DELETE 등이 있습니다.
</details>

<details>
  <summary>정은경</summary>
  클라이언트와 서버 사이에 이루어지는 요청과 응답 데이터를 전송하는 방식입니다. 서버가 수행해야 할 동작을 지정하는 요청을 보내는 방법입니다. GET, POST, PUT, PATCH, DELETE 등이 있습니다. 
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

5. **REST API와 RESTful 하다는 것이 무엇인지 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

REST는 HTTP URI를 통해 자원을 명시하고 HTTP Method를 통해 자원을 처리하도록 설계된 아키텍처입니다. 이러한 REST를 기반으로 만든 API가 바로 REST API입니다.

이 REST 설계 규칙을 잘 지켜서 설계된 프로그램을 RESTful하다고 표현합니다.

REST API 설계 원칙에는 일관된 인터페이스, 무상태성, 다중 계층 등이 있습니다.
</details>

<details>
  <summary>정은경</summary>
  REST API는 자원을 URI로 정의하고 HTTP 메서드를 사용하여 상태를 주고받는 것을 의미합니다.

  REST API의 설계 규칙을 올바르게 지킨 시스템을 RESTful 하다고 말할 수 있습니다.
  자원의 표현을 URI로 명확히 정의하고, 상태(HTTP 메서드)를 통해 자원을 조작하고, 클라이언트-서버 구조, 무상태성, 캐시 가능성 등의 특성을 만족해야 합니다. 
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

### 💡 추가로 공부해 온 내용

1. **DNS가 무엇인지 설명해주세요.**

<details>
  <summary>이지원</summary>

DNS는 Domain Name System의 약자로, 사람이 읽을 수 있는 도메인 이름을 머신이 읽을 수 있는 IP 주소로 변환하는 시스템입니다.
</details>

<details>
  <summary>정은경</summary>

DNS는 Domain Name System의 약자로, IP 주소와 같이 숫자로 이루어진 인터넷상의 컴퓨터 주소를 영문으로 알기 쉽게 바꿔주는 시스템입니다.
</details>
</br>

### 💫 공부한 내용 정리한 링크
| 이름 | 블로그 링크 |
|------|--------------|
|김영주||
|이지원|<a href="Network_jiwon_1118.md" target="_blank">github md파일</a>|
|정은경|<a href="https://velog.io/@jeg1124/series/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC" target="_blank">블로그 링크</a>|
|정진희||
