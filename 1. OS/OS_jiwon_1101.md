# 1주차 두번째 : 운영체제 (이지원)

### 🎨 공통 질문
<details>
<summary><strong>Blocking과 Non-Blocking에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

다른 요청의 작업을 처리하기 위해 현재 작업을 block(차단, 대기)하냐 안하냐의 유무를 나타내는 프로세스의 실행 방식

### 💬 블로킹/논블로킹은 제어권 여부의 차이

제어권 : 함수의 코드나 프로세스의 실행 흐름을 제어할 수 있는 권리 같은 것

**Blocking** : A 함수가 B 함수를 호출할 때, B 함수가 자신의 작업이 종료되기 전까지 A 함수에게 제어권을 돌려주지 않는 것, B 함수가 종료될 때까지 A 함수는 다른 일을 수행할 수 없음

![image](https://github.com/user-attachments/assets/8fae493e-1f45-45c4-b126-f7e46c9021ba)

**Non-Blocking** : A 함수가 B 함수를 호출할 때, 제어권은 A 함수가 그대로 가지고 있는 것, A 함수는 계속 제어권을 가지고 있기 때문에 B 함수를 호출한 이후에도 다른 일 수행 가능

![image](https://github.com/user-attachments/assets/ee50d650-76f5-4681-b196-d9b9266e4e70)

### 🤔 동기/비동기와 Blocking/Non-Blocking의 차이는?

동기/비동기 : 요청한 작업에 대해 완료 여부를 신경 써서 작업을 순차적으로 수행할지 아닌지에 대한 관점

블로킹/논블로킹 : 현재 작업이 block(차단, 대기) 되느냐 아니냐에 따라 다른 작업을 수행할 수 있는지에 대한 관점

### 💬 동기/비동기는 **작업 순서 처리 차이**

동기 작업은 요청한 작업에 대해 순서가 지켜지는 것

![image](https://github.com/user-attachments/assets/4e2d4edf-6027-4e7f-8e82-1e6a04f63a60)

비동기 작업은 순서가 지켜지지 않을 수 있다는 것

![image](https://github.com/user-attachments/assets/75c52ad7-d3af-4a5a-94bd-465d4d5c19c1)

➡️ 작업 3개를 요청했는데 응답에서 그 순서가 지켜진다면 동기, 어떤 게 먼저 올지 모른다면 비동기
</div>
</ul>
</div>
</details>
<details>
<summary><strong>Race Condition과 Critical Section이 무엇이고, 경쟁상태를 막기 위해 어떤 방법을 사용하는지 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

**Race Condition(경쟁 상태)** : 두 개 이상의 쓰레드가 공유자원에 대해 접근하려고 서로 경쟁하는 것

**Critical Section(임계영역)** : 프로세스 간에 공유 자원에 접근하는 데 있어 문제가 발생하지 않도록 한번에 하나의 프로세스만 접근할 수 있도록 보장해줘야 하는 영역

### 🚫 경쟁상태를 막기 위한 방법

**뮤텍스(Mutex)** 와 **세마포어(Semaphore)** 가 있는데, 이들은 상호 배제, 한정 대기, 진행 조건을 만족시키며 경쟁 상태 해결

- 상호 배제 : 하나의 프로세스가 임계 영역에 들어가 있다면 다른 프로세스는 들어갈 수 없음
- 한정 대기 : 다른 프로세스의 기아 방지를 위해 한번 임계 영역에 들어간 프로세스는 다음 번에 제한 ➡️ 특정 프로세스가 영원히 임계 영역에 들어가지 못하는 것을 방지
- 진행 : 어떠한 프로세스도 임계 영역을 사용하지 않는다면 임계 영역 외부의 어떠한 프로세스든 들어갈 수 있으며, 이때 프로세스끼리 서로 방해하지 않는 것

</div>
</ul>
</div>
</details>
<details>
<summary><strong>CPU Scheduling이 무엇인지 설명하고, CPU 스케줄링의 종류에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

**CPU Scheduling** : Ready 상태의 프로세스 중 어떤 프로세스에게 CPU 할당할지 결정하는 것

### 선점 스케줄링

하나의 프로세스가 CPU를 차지하고 있을 때, 우선순위가 높은 다른 프로세스가 현재 프로세스를 중단시키고 CPU를 점유하는 스케줄링 방식

- Round Robin(RR) : 프로세스마다 같은 크기의 시간 할당량을 주고 프로세스가 할당된 시간 내에 완료하지 못하면 준비 큐 리스트의 가장 뒤로 배치하는 방식
- Shortest Remaining Time First (SRTF) : CPU 점유 시간이 가장 짧은 프로세스를 먼저 수행하는 방식
- Multilevel Feedback Queue(다중 레벨 피드백 큐) : 각 단계마다 하나의 큐를 두고, 큐 시간 할당량 내에 처리하지 못하면 다음 큐로 보내는 방식

### 비선점 스케줄링

이미 할당된 CPU를 다른 프로세스가 강제로 빼앗아 사용할 수 없는 스케줄링 기법

- First Come First Served(FCFS) : 먼저 온 프로세스를 먼저 처리해주는 방식
- Shortest Job First (SJF) : CPU 점유 시간이 가장 짧은 프로세스를 먼저 수행하는 방식, SRTF 방식에서 선점 방식만 다름
- Highest Response Ratio Next : 대기 중인 프로세스 중 현재 Response Ratio(응답비율)가 가장 높은 것을 선택

</div>
</ul>
</div>
</details>
<details>
<summary><strong>메모리의 종류에 대해 설명하고, 종류가 여러가지인 이유에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

CPU에 가까운 순서대로 레지스터, 캐시, 주기억장치, 보조기억장치

물리적 메모리의 종류가 많은 이유는, 접근 속도에 따른 차이를 두기 위해서입니다. (레지스터 > 캐시 > 주기억장치 > 보조기억장치)

</div>
</ul>
</div>
</details>

### 💡 추가로 공부해 온 내용

<details>
<summary><strong>Mutex(뮤텍스)와 Semaphore(세마포어)에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

뮤텍스와 세마포어를 사용해 임계영역에서의 경쟁상태 제거 가능

### Mutex(뮤텍스)

- 공유 자원에 대한 접근을 제어하기 위한 상호 배제 기법 중 하나
- 공유 자원에 오직 1개만의 쓰레드(또는 프로세스)만 접근 가능
- Lock을 사용해 하나의 프로세스나 쓰레드를 단독으로 실행하게 함
    - Lock : 공유 자원을 하나의 쓰레드(또는 프로세스)가 사용하고 있을 때 다른 쓰레드가 공유 자원을 사용하지 못하도록 제한을 거는 것
- 1개만 접근 가능하므로 반드시 락을 획득한 프로세스가 락을 해제해야 함

### Semaphore(세마포어)

- 동시에 접근 가능한 쓰레드의 개수를 지정할 수 있어서, 세마포어 변수만큼의 쓰레드(또는 프로세스)가 접근 가능
    - 0과 1의 값만 갖는 세마포어 → 이진 세마포어(binary semaphore) (= 뮤텍스)
    - 도메인 제한이 없는 세마포어(0,1 뿐만아니라 2,3,4 등의 값들 또한 가질 수 있는) → 카운팅 세마포어(counting semaphore)
- 현재 수행중인 프로세스가 아닌 다른 프로세스가 세마포어를 해제 가능

</div>
</ul>
</div>
</details>
<details>
<summary><strong>컨텍스트 스위칭에 대해서 설명하고, 왜 컨텍스트 스위칭이 필요한지 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

**Context Switching** : 멀티 프로세스 환경에서 현재 진행중인 Task(프로세스 혹은 쓰레드)의 상태를 PCB에 저장하고, 다음에 진행할 Task의 상태 값으로 교체하는 작업

Context : CPU가 해당 프로세스를 실행하기 위한 해당 프로세스의 정보들

### 필요한 이유

- 여러 프로세스/스레드를 동시에 실행시키기 위해서
- ex) 작업이 실행되고 Blocking 된다면, CPU는 아무런 일을 하지 않고 오랜 기간동안 쉬게 됨 → 컨텍스트 스위칭을 통해 다른 프로세스나 쓰레드의 작업으로 전환한다면, CPU의 사용률을 높일 수 있음

</div>
</ul>
</div>
</details>
<details>
<summary><strong>프로세스 제어 블록 (PCB)에 대해 더 자세히 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### **프로세스 제어 블록 (Process Control Block, PCB)**

- 프로세스를 관리하기 위한 정보를 포함하는 OS 커널의 자료 구조
- 프로세스 상태 관리와 문맥교환(Context Switching)을 위해 필요
- 프로세스 생성 시 만들어지며 주기억장치에 유지됨

> 프로세스는 CPU를 할당받아 작업 처리 → 작업 처리 중 프로세스 전환이 발생하면 진행하던 작업을 PCB에 저장하고 CPU 반환 → 이후 다시 CPU 할당받으면 PCB에 저장되어 있는 내용 불러와 종료했던 시점부터 다시 작업 수행
>

</div>
</ul>
</div>
</details>
<details>
<summary><strong>커널이 무엇인지 설명하실 수 있나요?</strong></summary>
<div markdown="1">
<ul>
<div>

**커널** : 운영체제 중 항상 메모리에 올라가 있는 운영체제의 핵심 부분, 하드웨어와 응용 프로그램 사이에서 인터페이스를 제공하는 역할

✋ 커널은 항상 컴퓨터 자원들을 바라만 보고 있기에 사용자와의 상호작용은 지원하지 않음 → 사용자와의 직접전인 상호작용을 위해 프로그램 제공(ex. 쉘(Shell)이라는 명령어 해석기)

### 인터페이스로서의 커널

![image](https://github.com/user-attachments/assets/47288970-34e3-43a9-8958-14244f8f6a18)

- 커널 구성요소들이 존재하는 공간이 **Kernel Space**
- Kernel Space 위에는 사용자로 여겨지는 **User Space**가 있으며 여기에는 Task, Process들이 존재
- User Space와 Kernel Space 사이에는 보이지 않지만 **System Call Interface** 존재
    - User Space의 Task 또는 Process들이 커널이 관리하는 자원에 접근해야할 필요가 있을때 System Call Interface를 통해 Kernel Space의 자원관리자에게 요청이 전달되는 방식

⇒ **커널**은 사용자가 **System Call**을 통해 컴퓨터 자원을 사용할 수 있게해주는 **자원 관리자**
</div>
</ul>
</div>
</details>
<details>
<summary><strong>System Call은 무엇인가요?</strong></summary>
<div markdown="1">
<ul>
<div>

**System Call** : 사용자나 응용프로그램이 커널에서 제공하는 기능을 사용하기 위한 인터페이스

운영체제는 커널이 제공하는 서비스를 '시스템 콜'을 사용해야만 사용할 수 있도록 제한함으로써 컴퓨터 자원을 보호하면서 사용자나 응용프로그램에게 서비스를 제공할 수 있음

보통 직접적으로 시스템 콜을 사용하기 보다는 API(라이브러리 함수)를 통해 사용
</div>
</ul>
</div>
</details>
