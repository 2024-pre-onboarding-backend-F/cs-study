## 2주차 주제 : 자료구조

### 🎨 공통 질문 

1. **Array와 LinkedList의 차이점**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>
  
  Array는 순차적으로 데이터를 저장하는 자료구조로, 크기는 처음 생성할 때 정해지며 이후 변경이 불가능합니다. 또한, 검색이 빠르지만 삽입과 삭제가 느리다는 특징이 있습니다.

  LinkedList는 데이터를 저장하고 있는 각 노드를 서로 연결 시켜 만든 선형 자료구조로, 크기가 정해져 있지 않습니다. 또한, 삽입과 삭제는 빠르지만 검색이 느리다는 특징이 있습니다.
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

2. **Stack과 Queue의 개념 및 사용 사례**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

  Stack은 먼저 들어간 요소가 가장 나중에 나오게 되는 선입후출(LIFO, Last In First Out)의 구조를 가진 선형 자료구조로, 브라우저의 '뒤로가기'와 ctrl + z 되돌리기 연산 등에 사용됩니다.

  Queue는 먼저 들어간 요소가 가장 먼저 나오게 되는 선입선출(FIFO, First In First Out)의 구조를 가진 선형 자료구조로, 프린터 출력 요청, CPU 스케줄링 Ready 큐 등에 사용됩니다.
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

3. **Priority Queue 및 Heap**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>
  
  Priority Queue는 우선순위 큐로, 들어간 순서에 상관없이 우선순위가 높은 데이터를 먼저 꺼내기 위해 고안된 자료구조입니다.

  우선순위 큐는 주로 Array, LinkedList, Heap을 사용해 구현되는데, 시간복잡도 때문에 주로 Heap을 사용하는 방식으로 구현됩니다.

  Heap은 최댓값 또는 최솟값을 찾아내는 연산을 쉽게 하기 위해 고안된 구조로, 완전이진트리입니다. 힙은 최대힙(각 노드의 키값이 자식의 키값보다 작지 않은 자료구조)과 최소힙(각 노드의 키값이 자식의 키값보다 크지 않은 자료구조)이 있습니다.
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

4. **Hash Table과 Hash Collision 해결 방법**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

  Hash Table은 (Key, Value)로 데이터를 저장하는 자료구조로, 빠르게 데이터를 검색할 수 있는 자료구조를 의미합니다. 빠른 검색 속도를 제공하는 이유는 내부적으로 배열(버킷)을 사용하여 데이터를 저장하기 때문입니다.

  각 Key값은 해시함수에 의해 고유한 index를 가지게 되어 바로 접근할 수 있으므로 평균 $O(1)$의 시간 복잡도로 데이터를 조회할 수 있습니다.

  Hash Collision은 서로 다른 Key에 대해 같은 해시값을 갖는 경우 발생하는데, 해시 테이블에 접근하는 Key 값은 무한하지만 해시 함수를 통해 나온 Hash 값은 유한하기 때문입니다.

  Hash Collision을 해결하는 방법에는 크게 Separate Chaining(분리 연결법)과 Open Addressing(개방 주소법)이 있습니다.
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

5. **BST (Binary Search Tree)와 성능 개선 방법에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

  BST는 이진 탐색 트리로, 이진 탐색과 연결 리스트를 결합한 자료구조입니다. 왼쪽 트리의 모든 값은 반드시 부모 노드보다 작아야 하고, 오른쪽 트리의 값은 부모 노드보다 커야 하는 특징이 있습니다.

  BST의 탐색 연산은 트리의 높이에 영향을 받기 때문에 높이가 h일 때 시간 복잡도는 $O(h)$입니다. 그러나 트리의 균형이 한쪽으로 치우쳐진 경우 worst case가 되고 $O(N)$의 시간 복잡도를 가지게 됩니다.

  BST의 성능 개선 방법에는 BST의 양쪽 높이의 균형을 맞추는 방법이 있는데, 이 방법으로 BST를 개량한 AVL 트리와 Red-Black 트리가 있습니다.

  RBT(Red-Black Tree)는 BST를 기반으로 하는 트리 형식 자료구조로, BST의 삽입, 삭제 연산 과정에서 발생할 수 있는 문제점을 해결하기 위해 만들어졌습니다. 모든 노드는 빨간색 또는 검은색이고, 루트 노드는 검은색, 모든 리프 노드들은 검은색, 빨간색 노드의 자식은 검은색으로, 빨간색 노드가 연속으로 나올 수 없다는 특징을 가집니다.
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

6. **AVL 트리는 무엇인가요?**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

  BST를 기반으로 하는 트리 형식 자료구조로, 각 노드의 서브트리 높이 차이가 최대 1을 유지하도록 스스로 균형을 유지하는 트리를 의미합니다. 삽입과 삭제 연산을 수행할 때마다 트리의 균형 계수를 체크하고 균형 계수가 1보다 커질 때 회전(Rotation) 연산을 통해 균형을 유지한다는 특징을 가집니다.
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

7. **트리와 그래프의 차이에 대해서 설명할 수 있나요?**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

  그래프는 노드(하나의 점)와 노드 간을 연결하는 간선으로 구성된 자료 구조로, 방향이 있는 그래프와 방향이 없는 그래프가 모두 존재하고 루트 노드의 개념과 부모-자식 관계라는 개념이 없습니다.

  트리는 그래프와 같이 노드와 노드간을 연결하는 간선으로 구성된 자료구조로, 두 개의 노드 사이에 반드시 1개의 경로만 가지며, 사이클이 존재하지 않는 방향 그래프입니다. 그리고 부모-자식 관계가 성립하는 계층형 모델입니다.

  따라서 그래프는 트리보다 더 포괄적인 개념입니다.
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

8. **이진트리의 전위 / 중위 / 후위 순회가 무엇인가요? 설명해보세요**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

  전위 순회는 Root - Left - Right 순서로 노드를 순회하는 것으로, 루트를 먼저 방문합니다.

  중위 순회는 Left - Root - Right 순서로 노드를 순회하는 것으로, 루트를 중간에 방문합니다.

  후위 순회는 Left - Right - Root 순서로 노드를 순회하는 것으로, 루트를 후에 방문합니다.
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



</br>

### 💫 공부한 내용 정리한 링크
| 이름 | 블로그 링크 |
|------|--------------|
|김영주||
|이지원|<a href="data_structure_jiwon.md" target="_blank">github md파일</a>|
|정은경|<a href="https://velog.io/@jeg1124/series/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0" target="_blank">블로그 링크</a>|
|정진희||
