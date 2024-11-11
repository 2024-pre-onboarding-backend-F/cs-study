# 2주차 : 자료구조 (이지원)

### 🎨 첫번째 공통 질문
<details>
<summary><strong>Array와  LinkedList가 각각 무엇인지, 어떻게 다른지 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### Array(배열)

- 순차적으로 데이터를 저장하는 자료구조
- 크기는 고정길이로 처음 생성할 때 정해지며, 이후 변경 불가
- 데이터의 순서가 있기 때문에 0부터 시작하는 index가 존재하며, index를 사용해 특정 요소를 찾고 조작이 가능
- 순차적으로 존재하는 데이터의 중간에 요소가 삽입되거나 삭제되는 경우 그 뒤의 모든 요소들을 한 칸씩 뒤로 밀거나 당겨줘야 함 <br>
  ➡️ 이 문제를 해결하기 위해 나온 자료구조가 **LinkedList**

### LinkedList(연결리스트)

- 데이터를 저장하고 있는 각 노드를 서로 연결 시켜 만든 선형 자료구조
- 크기가 정해져 있지 않음
- 각각의 노드는 자기 자신 다음에 어떤 원소가 저장되어 있는지 알기 때문에 연결을 끊고 다음 노드로 이어주거나 중간 연결을 끊고 새로운 노드에 각각 연결되도록 설정하여 시간복잡도 `O(1)`로 삭제와 삽입을 진행
- 특정 값을 찾기 위해서는 연결리스트 내부의 원소를 모두 다 확인해야 함

### 정리

- Array는 검색이 빠르지만, 삽입, 삭제가 느림
- LinkedList는 삽입, 삭제가 빠르지만, 검색이 느림
</div>
</ul>
</div>
</details>
<details>
<summary><strong>Stack과 Queue에 대해 설명하고, 각각 어디에 사용되었는지 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### Stack

![image](https://github.com/user-attachments/assets/98a52e3a-6d7c-4d69-b0ae-e7d7b614f9b0)

- 먼저 들어간 요소가 가장 나중에 나오게 되는 `선입후출(LIFO, Last In First Out)`의 구조를 가진 선형 자료구조
- 주로 Array(배열)를 사용해 구현
- 브라우저의 '뒤로가기', ctrl + z 되돌리기 연산 등에 사용

### Queue

![image](https://github.com/user-attachments/assets/9486432c-d77a-4966-8a1a-939260ea4efe)

- 먼저 들어간 요소가 가장 먼저 나오게 되는 `선입선출(FIFO, First In First Out)`의 구조를 가진 선형 자료구조
- 주로 LinkedList(연결리스트)를 사용해 구현
- 프린터 출력 요청, CPU 스케줄링 Ready 큐 등에 사용
</div>
</ul>
</div>
</details>
<details>
<summary><strong>Priority Queue와 Heap에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### Prioritiy Queue(우선순위 큐)

- 들어간 순서에 상관없이 우선순위가 높은 데이터를 먼저 꺼내기 위해 고안된 자료구조

### Heap

- 최댓값 또는 최솟값을 찾아내는 연산을 쉽게 하기 위해 고안된 구조
- 완전이진트리
    - 각 노드가 최대 2개의 자식 노드를 갖는 트리 형태의 자료구조
    - 마지막 레벨을 제외한 모든 노드는 완전히 채워져 있어야 함
- 최대힙 : 각 노드의 키값이 자식의 키값보다 작지 않은 자료구조
- 최소힙 : 각 노드의 키값이 자식의 키값보다 크지 않은 자료구조

### 우선순위 큐 구현 방법

- Array, LinkedList, Heap 사용하는 방법
- 주로 Heap을 사용하는 방식으로 구현 ➡️ 시간복잡도 때문
</div>
</ul>
</div>
</details>
<details>
<summary><strong>Hash Table과 Hash Collision 해결 방법에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### Hash Table

- (Key, Value)로 데이터를 저장하는 자료구조, 빠르게 데이터를 검색할 수 있는 자료구조
- 빠른 검색 속도를 제공하는 이유는 내부적으로 배열(버킷)을 사용하여 데이터를 저장하기 때문
    - 버킷 : 실제 값이 저장되는 장소
- 각 Key값은 해시함수에 의해 고유한 index를 가지게 되어 바로 접근할 수 있으므로 평균 `O(1)`의 시간 복잡도로 데이터를 조회

### Hash Collision 발생 이유

- **Hash Collision(해시 충돌)** : 서로 다른 Key에 대해 같은 해시값을 갖는 경우
- 해시 테이블에 접근하는 Key 값은 무한하고, 해시 함수를 통해 나온 Hash 값은 유한하기 때문

### Hash Collision 해결 방법

- **Separate Chaining(분리 연결법)** : 동일한 버킷에 저장되어야하는 데이터에 체인을 걸어 찾는 데이터가 나올 때까지 계속 체인을 따라가는 방식
- **Open Addressing(개방 주소법)** : 저장해야하는 인덱스에 값이 있으면 다른 인덱스에 저장하는 방법
</div>
</ul>
</div>
</details>
<br>

### 🎨 두번째 공통 질문
<details>
<summary><strong>BST(Binary Search Tree)의 성능 개선 방법에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### BST (Binary Search Tree)

- **이진 탐색 트리**로, 이진 탐색과 연결 리스트를 결합한 자료구조
- 이진 탐색은 정렬된 리스트에서 검색 범위를 줄여 나가면서 검색 값을 찾는 알고리즘
- 왼쪽 트리의 모든 값은 반드시 부모 노드보다 작아야 하고, 오른쪽 트리의 값은 부모 노드보다 커야 하는 특징
- 탐색 연산은 트리의 높이에 영향을 받기 때문에 높이가 h일 때 시간 복잡도는 `O(h)`
- 트리의 균형이 한쪽으로 치우쳐진 경우 worst case가 되고 `O(N)`의 시간 복잡도 가짐

![image](https://github.com/user-attachments/assets/bb3dd014-0712-4588-92bc-2dab7cddafa4)

### 성능 개선 방법

- BST의 양쪽 높이의 균형을 맞추는 방법
    - AVL 트리
    - Red-Black 트리

### RBT(Red-Black Tree)

- BST를 기반으로 하는 트리 형식 자료구조로, BST의 삽입, 삭제 연산 과정에서 발생할 수 있는 문제점을 해결하기 위해 만들어짐
- 모든 노드는 빨간색 또는 검은색
- 루트 노드는 검은색
- 모든 리프 노드(NIL)들은 검은색
    - NIL : null leaf, 자료를 갖지 않고 트리의 끝을 나타내는 노드
- 빨간색 노드의 자식은 검은색으로, 빨간색 노드가 연속으로 나올 수 없음
- 모든 리프 노드에서 black depth는 같음 = 리프 노드에서 루트 노드까지 가는 경로에서 만나는 검은색 노드의 개수는 동일

![image](https://github.com/user-attachments/assets/71778e96-35d8-4448-9b2c-2b2327c68a88)

</div>
</ul>
</div>
</details>
<details>
<summary><strong>AVL 트리는 무엇인가요?</strong></summary>
<div markdown="1">
<ul>
<div>

- 각 노드의 서브트리 높이 차이가 최대 1을 유지하도록 스스로 균형을 유지하는 트리
    - 균형 계수(Balance Factor, BF) : 서브트리의 높이 차이
- 노드의 균형 계수는 항상 -1, 0, 1
- 삽입과 삭제 연산을 수행할 때마다 트리의 균형 계수를 체크하고 균형 계수가 1보다 커질 때 회전(Rotation) 연산을 통해 균형 유지
</div>
</ul>
</div>
</details>
<details>
<summary><strong>트리와 그래프의 차이에 대해서 설명할 수 있나요?</strong></summary>
<div markdown="1">
<ul>
<div>

<img width="400" alt="트리와 그래프" src="https://github.com/user-attachments/assets/89c06807-fddd-4fa9-8897-1c6787738f31" width="90%" height="100%">

그래프는 트리보다 더 포괄적인 개념

### 그래프

- 노드(하나의 점)와 노드 간을 연결하는 간선으로 구성된 자료 구조
- 순환 혹은 비순환 구조를 이룸
- 방향이 있는 그래프와 방향이 없는 그래프가 존재
- 루트 노드의 개념 X & 부모-자식 관계라는 개념 X

### 트리

- 그래프와 같이 노드와 노드간을 연결하는 간선으로 구성된 자료구조
- 두 개의 노드 사이에 반드시 1개의 경로만 가지며, 사이클이 존재하지 않는 방향 그래프
- 부모-자식 관계가 성립하는 계층형 모델
</div>
</ul>
</div>
</details>
<details>
<summary><strong>이진트리의 전위 / 중위 / 후위 순회가 무엇인가요? 설명하고, 자신이 직무 언어로 순회 결과를 코딩해보세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### 전위 순회(Pre-order)

- Root - Left - Right 순서로 노드 순회
- 루트를 **먼저** 방문

### 중위 순회(In-order)

- Left - Root - Right 순서로 노드 순회
- 루트를 **중간에** 방문

### 후위 순회(Post-order)

- Left - Right - Root 순서로 노드 순회
- 루트를 **후에** 방문

<br>

![image](https://github.com/user-attachments/assets/3aba3a20-c29f-4389-8935-2b70b466f9da)

### 전위 순회 결과

- A B D C E F G

### 중위 순회 결과

- D B A E C F G

### 후위 순회 결과

- D B E G F C A
</div>
</ul>
</div>
</details>
