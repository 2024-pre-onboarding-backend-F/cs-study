## 1주차 주제 : 운영체제

### 🎨 공통 질문 

1. **Blocking과 Non-Blocking에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>
  
  다른 요청의 작업을 처리하기 위해 현재 작업을 block(차단, 대기)하냐 안하냐의 유무를 나타내는 프로세스의 실행 방식입니다.

  다시 말해 블로킹, 논블로킹은 제어권 여부의 차이로, 이때 제어권이란 함수의 코드나 프로세스의 실행 흐름을 제어할 수 있는 권리 같은 것입니다.

  **Blocking**은 A 함수가 B 함수를 호출할 때, B 함수가 자신의 작업이 종료되기 전까지 A 함수에게 제어권을 돌려주지 않는 것입니다. 따라서 B 함수가 종료될 때까지 A 함수는 다른 일을 수행할 수 없습니다.

  **Non-Blocking**은 A 함수가 B 함수를 호출할 때, 제어권은 A 함수가 그대로 가지고 있는 것입니다. A 함수는 계속 제어권을 가지고 있기 때문에 B 함수를 호출한 이후에도 다른 일을 수행할 수 있습니다.

  ### ➕ 동기/비동기와 Blocking/Non-Blocking의 차이는?

  - 동기/비동기는 요청한 작업에 대해 완료 여부를 신경 써서 작업을 순차적으로 수행할지 아닌지에 대한 관점입니다.

  - 블로킹/논블로킹은 현재 작업이 block(차단, 대기) 되느냐 아니냐에 따라 다른 작업을 수행할 수 있는지에 대한 관점입니다.
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

2. **Race Condition과 Critical Section이 무엇이고, 경쟁상태를 막기 위해 어떤 방법을 사용하는지 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

  Race Condition은 경쟁상태로, 두 개 이상의 쓰레드가 공유자원에 대해 접근하려고 서로 경쟁하는 것을 의미합니다.

  Critical Section은 임계영역으로, 프로세스 간에 공유 자원에 접근하는 데 있어 문제가 발생하지 않도록 한번에 하나의 프로세스만 접근할 수 있도록 보장해줘야 하는 영역을 의미합니다.

  경쟁상태를 막기 위한 방법에는 크게 뮤텍스(Mutex)와 세마포어(Semaphore)가 있는데, 이들은 상호 배제, 한정 대기, 진행 조건을 만족시키며 경쟁 상태를 해결합니다.
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

3. **CPU Scheduling이 무엇인지 설명하고, CPU 스케줄링의 종류에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

  CPU Scheduling이란 Ready 상태의 프로세스 중 어떤 프로세스에게 CPU 할당할지 결정하는 것을 의미합니다.

  CPU 스케줄링은 크게 선점 스케줄링과 비선점 스케줄링으로 나눌 수 있습니다.

  **선점 스케줄링**은 하나의 프로세스가 CPU를 차지하고 있을 때, 우선순위가 높은 다른 프로세스가 현재 프로세스를 중단시키고 CPU를 점유하는 스케줄링 방식을 의미하고, **비선점 스케줄링**은 이미 할당된 CPU를 다른 프로세스가 강제로 빼앗아 사용할 수 없는 스케줄링 기법을 의미합니다.
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

4. **메모리의 종류에 대해 설명하고, 종류가 여러가지인 이유에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>
  
  CPU에 가까운 순서대로 레지스터, 캐시, 주기억장치, 보조기억장치가 있습니다.

  물리적 메모리의 종류가 많은 이유는, 접근 속도에 따른 차이를 두기 위해서입니다.
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

1. Mutex(뮤텍스)와 Semaphore(세마포어)에 대해 설명해주세요.

<details>
  <summary>이지원</summary>
  
  뮤텍스와 세마포어를 사용해 임계영역에서의 경쟁상태를 제거할 수 있습니다.

  **뮤텍스**는 공유 자원에 오직 1개의 쓰레드(또는 프로세스)만 접근 가능하고, **세마포어**는 동시에 접근 가능한 쓰레드의 개수를 지정할 수 있어서, 세마포어 변수만큼의 쓰레드(또는 프로세스)가 접근 가능합니다.

  이때, 0과 1의 값만 갖는 세마포어는 이진 세마포어(binary semaphore)로 뮤텍스와 같고, 도메인 제한이 없는 세마포어는 카운팅 세마포어(counting semaphore)라고 합니다.
</details>

</br>

2. 컨텍스트 스위칭에 대해서 설명하고, 왜 컨텍스트 스위칭이 필요한지 설명해주세요.

<details>
  <summary>이지원</summary>
  
  Context Switching은 멀티 프로세스 환경에서 현재 진행중인 Task(프로세스 혹은 쓰레드)의 상태를 PCB에 저장하고, 다음에 진행할 Task의 상태 값으로 교체하는 작업을 의미합니다.

  이때 Context란, CPU가 해당 프로세스를 실행하기 위한 해당 프로세스의 정보들을 의미합니다.

  컨텍스트 스위칭이 필요한 이유는 여러 프로세스/스레드를 동시에 실행시키기 위해서입니다. 만약 작업이 실행되고 Blocking 된다면, CPU는 아무런 일을 하지 않고 오랜 기간동안 쉬게 되는데, 컨텍스트 스위칭을 통해 다른 프로세스나 쓰레드의 작업으로 전환한다면 CPU의 사용률을 높일 수 있기 때문입니다.
</details>

</br>

3. 프로세스 제어 블록 (PCB)에 대해 더 자세히 설명해주세요.

<details>
  <summary>이지원</summary>
  
  프로세스 제어 블록(PCB)은 프로세스를 관리하기 위한 정보를 포함하는 OS 커널의 자료 구조로, 프로세스 상태 관리와 문맥교환(Context Switching)을 위해 필요합니다.
</details>

</br>

4. 커널이 무엇인지 설명하실 수 있나요?

<details>
  <summary>이지원</summary>
  
  커널은 운영체제 중 항상 메모리에 올라가 있는 운영체제의 핵심 부분으로, 하드웨어와 응용 프로그램 사이에서 인터페이스를 제공하는 역할을 합니다.

  커널은 항상 컴퓨터 자원들을 바라만 보고 있기에 사용자와의 상호작용은 지원하지 않습니다. 따라서 사용자와의 직접적인 상호작용을 위해 쉘(Shell)이라는 명령어 해석기같은 프로그램을 제공합니다.

  커널 구성요소들이 존재하는 공간이 Kernel Space이고, Kernel Space 위에는 사용자로 여겨지는 User Space가 있으며 여기에는 Task, Process들이 존재합니다. User Space와 Kernel Space 사이에는 보이지 않지만 System Call Interface 존재하는데요, User Space의 Task 또는 Process들이 커널이 관리하는 자원에 접근해야 할 필요가 있을 때 System Call Interface를 통해 Kernel Space의 자원관리자에게 요청이 전달됩니다. 따라서 커널은 사용자가 System Call을 통해 컴퓨터 자원을 사용할 수 있게 해주는 자원 관리자라고 할 수 있습니다.
</details>

</br>

5. System Call은 무엇인가요?

<details>
  <summary>이지원</summary>
  
  System Call은 사용자나 응용프로그램이 커널에서 제공하는 기능을 사용하기 위한 인터페이스를 의미합니다.

  운영체제는 커널이 제공하는 서비스를 '시스템 콜'을 사용해야만 사용할 수 있도록 제한함으로써 컴퓨터 자원을 보호하면서 사용자나 응용프로그램에게 서비스를 제공할 수 있습니다.
</details>

</br>

### 💫 공부한 내용 정리한 링크
| 이름 | 블로그 링크 |
|------|--------------|
|김영주||
|이지원|<a href="OS_jiwon_1101.md" target="_blank">github md파일</a>|
|정은경||
|정진희||
