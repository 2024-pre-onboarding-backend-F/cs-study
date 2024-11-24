# 4주차 첫번째 : 네트워크 (이지원)

### 🎨 공통 질문
<details>
<summary><strong>OSI 7 Layer의 각 계층에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### OSI 7 Layer

- 네트워크에서 통신이 일어나는 과정을 7단계로 나눈 것

  ![image](https://github.com/user-attachments/assets/b76389ec-cb29-4d80-99db-99f971ed1af9)

### 1 계층(물리 계층)

- 데이터를 전기 신호로 바꾸어주는 계층
- 데이터 단위는 bit

### 2 계층(데이터링크 계층)

- 데이터의 물리적인 전송과 에러 검출, 흐름 제어를 담당하는 계층
- 데이터 단위는 frame
- ex. 이더넷

### 3 계층(네트워크 계층)

- 데이터를 목적지까지 가장 안전하고 빠르게 전달하기 위한 계층
- 데이터 단위는 Packet
- ex. Router

### 4 계층(전송 계층)

- 최종 수신 프로세스로 데이터의 전송을 담당하는 계층
- 데이터 단위는 Segment
- ex. TCP, UDP

### 5 계층(세션 계층)

- 컴퓨터끼리 통신을 하기 위해 세션을 만드는 계층

### 6 계층(표현 계층)

- 데이터의 형식(Format)을 정의하는 계층

### 7 계층(응용 계층)

- 사용자에게 통신을 위한 서비스를 제공하는 계층
</div>
</ul>
</div>
</details>
<details>
<summary><strong>TCP Connection 시 3-way handshaking에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### TCP

- 연결 지향적 프로토콜
- 장치들 사이에 논리적인 접속을 성립하기 위해 연결을 설정해신뢰성을 보장하는 연결형 서비스
- 3-way handshaking 과정을 통해 연결을 설정

### 3-way handshaking

- 발신지와 수신지 사이에 논리적인 접속(세션)을 성립하는 과정

### 3-way handshaking 과정

```
💡 간단히 표현
#1. Client -> Server : 내 말 들려?
#2. Server -> Client : 어 잘 들려! 내 말은 들려?
#3. Client -> Server : 잘 들려!
```

![image](https://github.com/user-attachments/assets/e1f3660d-94e4-4f3a-a07d-188da174d12b)

> SYN(synchronize sequence numbers) : 연결 확인을 보내는 무작위의 숫자 값 (내 말 들려?)
> 
> ACK(acknowledgements) : Client 혹은 Server로부터 받은 SYN에 1을 더해 SYN을 잘 받았다는 ACK (잘 들려!)
>

1. 먼저 Open한 클라이언트가 SYN(내 말 들려?)을 보내고 ***S*YN_SENT** 상태로 대기

2. 서버는 **SYN-RECEIVED** 상태로 바꾸고 SYN과 응답 ACK(어 잘 들려! 내 말은 들려?) 보냄

3. SYN과 응답 ACK를 받은 클라이언트는 **ESTABLISHED** 상태로 변경하고 서버에게 응답 ACK(잘 들려!) 보냄

4. 응답 ACK를 받은 서버는 **ESTABLISHED** 상태로 변경

| **상태** | **설명** |
| --- | --- |
| SYN-SENT | SYN을 요청한 상태 |
| SYN-RECEIVED | SYN 요청을 받고 상대방의 응답을 기다리는 중 |
| ESTABLISHED | 연결 수립이 완료된 상태, 서로 데이터 교환 가능 |

</div>
</ul>
</div>
</details>
<details>
<summary><strong>TCP와 UDP의 차이에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### TCP

- 연결형 서비스

- 3-way handshaking 과정을 통해 연결을 설정하기 때문에 높은 신뢰성 보장

- 속도가 비교적 느리다는 단점

### UDP

- 비연결형 서비스

- 3-way handshaking을 사용하지 않기 때문에 신뢰성이 떨어지는 단점

- 데이터 수신 여부를 확인하지 않기 때문에 속도가 빠르다는 장점

|  | TCP | UDP |
| --- | --- | --- |
| 연결 방식 | 연결형 서비스 | 비연결형 서비스 |
| 패킷 교환 방식 | 가상 회선 방식 | 데이터그램 방식 |
| 전송 순서 | 전송 순서 보장 | 전송 순서가 바뀔 수 있음 |
| 수신 여부 확인 | 수신 여부를 확인함 | 수신 여부를 확인하지 않음 |
| 통신 방식 | 1:1 통신 | 1:1 OR 1:N OR N:N 통신 |
| 신뢰성 | 높음 | 낮음 |
| 속도 | 느림 | 빠름 |

</div>
</ul>
</div>
</details>
<details>
<summary><strong>HTTP Method에는 어떤 것들이 있는지 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### HTTP Method

- 클라이언트가 서버에게 사용자 요청의 목적을 알리는 **수단**

| **종류** | **기능** |
| --- | --- |
| GET | 데이터 조회 |
| POST | 요청 데이터 처리(보통 데이터 등록 시 사용) |
| PUT | 데이터 변경 (해당 데이터가 없으면 생성) |
| PATCH | 일부 데이터만 변경 |
| DELETE | 데이터 삭제 |

</div>
</ul>
</div>
</details>
<details>
<summary><strong>REST API와 RESTful 하다는 것이 무엇인지 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### REST API

- REST : HTTP URI를 통해 자원을 명시하고 HTTP Method를 통해 자원을 처리하도록 설계된 아키텍처
- 이러한 REST를 기반으로 만든 API가 REST API

### RESTful

- REST 설계 규칙을 잘 지켜서 설계된 프로그램을 **RESTful하다**고 표현

### **REST API 설계 원칙**

1. Uniform Interface (일관된 인터페이스)
    
    데이터를 식별 가능하게 해야 한다는 원칙
    
    1. URL은 명사를 사용
    2. URL은 소문자를 사용
    3. URL은 복수형을 사용
    4. 구분자는 하이픈(-)을 사용
    5. URL 마지막엔 슬래시를 포함하지 않음
    6. 파일 확장자는 포함하지 않음

2. Client Server
    
    클라이언트와 서버는 반드시 분리되어야 하며, 클라이언트는 데이터를 서버에 요청하고 서버는 클라이언트의 요청에 따른 데이터를 응답해야 함
    
3. Stateless HTTP (무상태성)
    
    클라이언트의 모든 요청에는 해당 요청을 이해할 수 있는 모든 정보가 포함되어야 함
    
    서버는 HTTP 요청에 대한 어떤 것도 저장하지 않음
    
4. Cacheable
    
    요청을 통해 보내는 자료들은 저장되어야 함
    
5. Layered System (다중 계층)
    
    요청된 정보를 검색하는데 계층 구조로 분리되어 있어야 함
    
6. Code on Demand
    
    서버가 클라이언트에서 실행시킬 수 있는 로직을 전송하여 클라이언트의 기능을 확장시킬 수 있음
</div>
</ul>
</div>
</details>
<br>

### 💡 추가로 공부해 온 내용
<details>
<summary><strong>DNS가 무엇인지 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### **DNS**

- Domain Name System
- 사람이 읽을 수 있는 도메인 이름(예: www.amazon.com)을 머신이 읽을 수 있는 IP 주소(예: 192.0.2.44)로 변환하는 시스템
</div>
</ul>
</div>
</details>
