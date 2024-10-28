## 1주차 주제 : 운영체제

### 🎨 공통 질문 

1. **OS(운영체제)가 무엇인지 설명해주실 수 있나요?**

<details>
  <summary>김영주</summary>

  > 운영체제란 <u>하드웨어</u>를 사용하기 쉽게 만들어주는 인터페이스입니다. 사용자가 <u>효율적</u>으로 쓸 수 있게 <u>관리</u>해줍니다.

</details>

<details>
  <summary>이지원</summary>
  <!-- 내용 -->
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

2. **프로세스와 쓰레드에 대해 설명하고, 둘의 차이에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>

  > <b>프로세스</b>란 <u>운영체제</u>로부터 자원을 할당받은 작업의 단위입니다. 운영 체제에서 각 개별로 <u>Code, Data, Stack, Heap</u>의 형식으로 할당 받습니다.</br></br> <b>스레드</b>란 <u>프로세스</u>가 할당받은 자원을 이용하는 실행 흐름의 단위입니다. 스레드는 <u>Stack</u>은 개별로 할당 받고, <u>Code, Data, Heap</u>은 자원을 공유합니다.

</br>

**✅ 해당 파트는 추가 질문이 들어오면 답할 예상 답안입니다.** 

> <b>멀티 프로세스</b>란 <u>하나의 프로그램</U>을 <u>여러 개의 프로세스로 구성</u>하여 각 프로세스가 <b>병렬적으로 작업을 수행</b>합니다. </br></br> <b>장점</b>으로는 안전성이 있고, <b>단점</b>으로는 각각 독립된 메모리 영역을 갖고 있어 <u>작업량이 많을수록 오버헤드가 발생</u>합니다. <u>Context Switching으로 인한 성능 저하도 발생</u>할 수 있습니다.

> <b>멀티 스레드</b>란 <u>하나의 응용 프로그램</u>에서 <u>여러 스레드를 구성</u>해 각 스레드가 <b>하나의 작업을 처리</b>하는 것입니다.</br></br>
<b>장점</b>으로는 독립적인 프로세스에 비해 공유 메모리만큼 시간, 자원 손실이 감소하고, 전역 변수와 정적 변수에 대한 자료 공유가 가능합니다.
<b>단점</b>으로는 안정성 문제, <b>하나의 스레드가 데이터 공간을 망가트리면, 모든 스레드가 작동 불능 상태가 됩니다.</b>
 
</details>

<details>
  <summary>이지원</summary>
  <!-- 내용 -->
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

3. **메모리의 힙 영역과 스택 영역의 차이에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>

> <b>HEAP 영역</b>은 <b>프로그래머가 자율적으로 메모리 크기를 할당</b>할 수 있는 영역입니다. 또한, 힙은 할당된 영역을 반납해줘야 하므로 <u>동적할당 영역</u>에 속합니다. 

> <b>STACK 영역</b>은 <b>지역변수가 할당되는 영역</b>으로 함수가 호출되면 할당되었습니다. <u>함수의 종료시 반납되는 영역</u>입니다.

</br>

**➕ HEAP과 STACK 영역 설명 추가로 덧붙일 수 있는 내용**

> HEAP 영역은 런타임 시 크기가 결정되며, 크기가 제한되어 있지 않습니다. 주소 할당은 낮은 주소에서 높은 주소로 채워집니다. </br></br> STACK 영역은 컴파일 시 크기가 결정됩니다. 주소 할당은 높은 주소에서 낮은 주소로 할당됩니다. 힙에 비해 빠르고, 종료에 따라 소멸되므로 별다른 관리가 필요 없습니다.

>메모리의 위쪽에 위치할수록 낮은 주소입니다. 

</details>

<details>
  <summary>이지원</summary>
  <!-- 내용 -->
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

4. **DeadLock(교착상태)에 대해 설명하고, 해결 방법에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  
> <b>데드락</b>이란 <u>두 개 이상의 프로세스나 스레드가 서로 자원을 얻지 못해서 다음 처리를 하지 못하는 상태 시스템적으로 한정된 자원을 여러 곳에서 사용하려고 할 때 발생</u>합니다. <b>무한히 다음 자원을 기다리게 되는 상태</b>를 말합니다.


> 데드락이 일어나는 경우에는 4가지의 발생 조건이 있습니다. </br></br>
• <b>상호 배제(Mutual exclusion) :</b> 자원은 한번에 한 프로세스만 사용할 수 있다.
</br>• <b>점유 대기(Hold and wait) :</b> 최소한 하나의 자원을 점유하고 있으면서 다른 프로세스에 할당되어 사용하고 있는 자원을 추가로 점유하기 위해 대기하는 프로세스가 존재해야 한다.
</br><b>• 비선점(No preemption) :</b> 다른 프로세스에 할당된 자원은 사용이 끝날 때까지 강제로 빼앗을 수 없다.
</br>• <b>순환 대기(Circular wait) :</b> 프로세스의 집합에서 순환 형태로 자원을 대기하고 있어야 한다. 

> 데드락을 예방과 회피하는 방법에는 3가지의 주된 방법이 있습니다.
</br></br>• <b>예방(prevention) :</b> 교착 상태 발생 조건 중 하나를 제거하면서 해결한다 (자원 낭비 엄청 심함)
</br>• <b>회피(avoidance) :</b> 교착 상태 발생 시 피해나가는 방법
</br>• <b>회복(Recovery) :</b> 교착 상태 일으킨 프로세스를 종료하거나, 할당된 자원을 해제시켜 회복시키는 방법

</details>

<details>
  <summary>이지원</summary>
  <!-- 내용 -->
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

5. **동시성과 병렬성이 어떻게 다른지 설명해주세요.**

<details>
  <summary>김영주</summary>

> <b>동시성</b>이란 <b>주기억장치에 여러 프로세스를 적재해서 Context Switching을 통해 동시에 실행되는 것 처럼 보이게 하는 것을 의미</b>합니다. <u>싱글 코어에서 멀티스레드를 동작시키기 위한 방식</u>입니다.

> <b>병렬성</b>이란 <b>실제로 동시에 여러 프로세스를 병렬적으로 실행하는 방식</b>입니다. 병렬적으로 실행하기 위해서는 <u>CPU가 멀티코어</u>여야 합니다. 

</details>

<details>
  <summary>이지원</summary>
  <!-- 내용 -->
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
1. Context Switing에 대해 설명해주세요. (프로세스와 스레드 꼬리 질문)

<details>
  <summary>김영주</summary>

  > <b>Context Switching</b>이란 <b>프로세스의 상태 정보를 저장하고 복원하는 일련의 과정</b>입니다. 프로세스는 각 독립된 메모리 영역을 할당받아 사용되므로, 캐시 메모리 초기화와 같은 무거운 작업이 진행되었을 때 오버헤드가 발생할 문제가 존재합니다.
</details>

<details>
  <summary>정은경</summary>
  <!-- 내용 -->
</details>

</br>

2. 인터럽트(Interrupt)에 대해 설명해 주세요.

<details>
  <summary>김영주</summary>
  
  > <b>Interrupt(인터럽트)</b>란 <b>프로그램을 실행하고 있는 도중에 입출력 요청 혹은 예외 상황을 처리해야 하면 실행하던 프로그램을 멈추고 CPU가 해당 작업을 처리하도록 하는 것을 의미</b>합니다.

</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

3. 시스템 콜(System call)에 대해 설명해 주세요.

<details>
  <summary>김영주</summary>
  
  > <b>시스템 콜(System call)</b>이란 <b>fork( ), exec( ), wait( )와 같은 것들은 Process 생성과 제어를 위한 것</b>입니다. <b>사용자나 응용프로그램이 커널에서 제공하는 기능을 사용하기 위한 인터페이스</b>입니다.

</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

4. PCB에 대해 설명해 주세요.
<details>
  <summary>김영주</summary>
  
> <b>PCB(Process Control Block)</b>란 <u>프로세스 메타데이터들을 저장해 놓는 곳이며, 한 PCB 안에는 한 프로세스의 정보가 담깁니다.</u> 한마디로 <b>프로세스를 관리하기 위한 정보를 포함하는 OS 커널의 자료 구조</b>입니다.

**➕ PCB 설명 추가로 덧붙일 수 있는 내용**

> <u>프로세스는 CPU를 할당받아 작업을 처리하다가, CPU를 선점 당하게 되면 진행 중이던 작업 내용을 PCB에 저장하고 CPU를 반환합니다. 이후에 다시 CPU를 할당받으면 PCB로 부터 진행이 끊겼던 부분에서 다시 작업을 실행합니다</u> 프로세스 식별자, 상태, PC(프로그램 카운터, 다음 실행할 명령의 주소 가르킴), 메모리 관리 정보 등을 가지고 있습니다.

</details>

</br>

5. 세마포어와 뮤텍스에 대한 개념과 차이에 대해 설명해 주세요.
<details>
  <summary>김영주</summary>
  
> <b>세마포어</b>란 <b>멀티프로그래밍 환경에서 공유 자원에 대한 접근을 제한하는 방법</b>입니다. <u>1개만 접근 가능하므로 반드시 락을 획득한 프로세스가 락을 해제</u>해야 합니다.

> <b>뮤텍스</b>란 <b>임계 구역을 가진 스레드들의 실행시간이 서로 겹치지 않고 각각 단독으로 실행되게 하는 기술</b>입니다. <u>현재 수행중인 프로세스가 아닌 다른 프로세스가 세마포어를 해제</u>할 수 있습니다.

> 이진 세마포어는 뮤텍스와 동일하다고 볼 수 있습니다. 이진 세마포어가 아닌 나머지 세마포어를 카운팅 세마포어라고 부릅니다.

> 세마포어와 뮤텍스의 차이점은 <b>세마포어는 공유 자원에 세마포어의 변수만큼 프로세스(or 쓰레드)가 접근할 수 있습니다.</b> 반면에 뮤텍스는 <b>오직 1개만의 프로세스(or 쓰레드)만 접근이 가능</b>합니다.

</details>

</br>

6. 페이징과 세그먼트 차이에 대해 설명해 주세요.
<details>
  <summary>김영주</summary>

> <b>페이징</b>이란 <b>고정 크기</b>이며, 메모리는 해당 페이지와 <u>동일한 크기의 프레임으로 분리</u>해서 <u>메인 메모리에 불연속적으로 저장하는 방식</u>입니다. <u>'내부단편화'</u>가 발생할 수 있습니다.

> <b>세그먼테이션</b>이란 <b>가변 크기</b>이며, <u>세그먼트로 분리하고 메모리에 적재</u>합니다. 주로 <u><b>논리적인 블록단위</b> 세그먼트로 Code, Data, Stack & Heap으로 분리</u>할 수 있습니다. 세그멘테이션 역시 <u>'외부 단편화'</u>가 발생합니다. 

</details>

</br>


### 💫 공부한 내용 정리한 링크
| 이름 | 블로그 링크 |
|------|--------------|
|김영주|<a href="https://kimeyou.tistory.com/124" target="_blank">Ctrl 또는 Command 눌러서 새 창에서 열기</a>|
|이지원||
|정은경||
|정진희||