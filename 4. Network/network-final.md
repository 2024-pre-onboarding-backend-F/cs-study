## 4주차 주제 : 네트워크

### 🎨 공통 질문

1. **전송계층과 데이터링크 계층 모두 신뢰성 관련 기능을 제공하는데, 어떤 차이가 있나요?**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

전송 계층과 데이터링크 계층은 오류 제어, 흐름 제어, 데이터 순서화 등을 제공하는 면에서 비슷합니다.

하지만 전송 계층은 논리적으로 1:1로 연결된 종단간 호스트 사이의 전송이라면, 데이터링크 계층은 물리적으로 1:1로 연결된 호스트 사이의 전송으로, 직접 묶여있는 호스트-노드 또는 노드-노드 간의 전송이라는 차이가 있습니다.
</details>

<details>
  <summary>정은경</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

2. **www.google.com 도메인을 브라우저에 입력했을 때 일어나는 일을 순차적으로 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

사용자가 www.google.com을 브라우저 주소창에 입력하면 브라우저는 DNS 서버에 도메인 네임으로 서버의 IP 주소를 찾습니다.

이후 IP 주소로 웹 서버에 TCP 3-way handshake로 연결이 수립되고, TCP 연결이 완료되면 웹 서버로 HTTP 요청 메시지를 보냅니다.

서버는 요청을 처리하고 HTTP 응답 메시지를 보내고, 브라우저에 도착한 HTTP 응답 메시지는 웹 페이지 데이터로 변환되고, 웹 브라우저에 의해 출력됩니다.
</details>

<details>
  <summary>정은경</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

3. **쿠키와 세션이 왜 필요한지, 어떻게 다른지 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

HTTP 프로토콜은 비연결성과 무상태의 특징이자 약점을 가지고 있습니다. 따라서 서버는 클라이언트가 누구인지 매번 확인해야 하는 번거로움이 있기 때문에 이 번거로움을 보완하기 위해 쿠키와 세션이 탄생했습니다.

쿠키는 사용자의 컴퓨터에 저장하는 작은 기록 정보 파일이고 세션은 일정 시간 동안 같은 사용자(브라우저)로부터 들어오는 일련의 요구를 하나의 상태로 보고, 그 상태를 유지시키는 기술입니다.

쿠키는 클라이언트 로컬에 저장되기 때문에 보안에 취약하지만 세션은 session id만 쿠키로 저장하고 이를 구분해 서버에서 처리하기 때문에 보안성이 높다는 차이가 있습니다.

또한 쿠키는 정보가 쿠키에 있기 때문에 서버에 요청시 속도가 빠르지만 세션은 정보가 서버에 있기 때문에 처리가 요구되어 속도가 비교적 느리다는 차이가 있습니다.
</details>

<details>
  <summary>정은경</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

4. **세션 기반 인증과 토큰 기반 인증은 각각 어느 경우에 적합한지 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

세션 기반 인증은 클라이언트로부터 요청을 받으면 클라이언트의 상태 정보를 저장하므로 Stateful한 구조를 가지고, 토큰 기반 인증은 상태 정보를 서버에 저장하지 않으므로 Stateless한 구조를 가집니다.

단일 도메인이라면 세션 기반 인증이, 아니라면 토큰 기반 인증이 적합합니다.

세션을 관리할 때 사용되는 쿠키는 단일 도메인 및 서브 도메인에서만 작동하도록 설계되어 있어서 여러 도메인에서 관리하는 것은 어렵기 때문입니다.
</details>

<details>
  <summary>정은경</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

### 💡 추가로 공부해 온 내용
1. **HTTP의 특징에 대해 설명해주세요.**

<details>
  <summary>이지원</summary>

HTTP는 Hyper Text Transfer Protocol의 약자로, 데이터를 주고 받기 위한 프로토콜로서 평문 데이터를 전송하는 프로토콜입니다.

HTTP는 클라이언트가 서버에 요청(Request)을 했을 때, 그 요청에 맞는 응답(Response)을 보낸 후 연결을 끊는 처리 방식으로 비연결 지향이라는 특징과, 커넥션을 끊는 순간 클라이언트와 서버의 통신이 끝나며 상태 정보는 유지하지 않는 특성을 가집니다.
</details>

</br>

### 💫 공부한 내용 정리한 링크
| 이름 | 블로그 링크 |
|------|--------------|
|김영주||
|이지원|<a href="Network_jiwon_1122.md" target="_blank">github md파일</a>|
|정은경||
|정진희||
