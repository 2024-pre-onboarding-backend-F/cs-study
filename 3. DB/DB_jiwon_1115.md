# 3주차 두번째 : 데이터베이스 (이지원)

### 🎨 공통 질문
<details>
<summary><strong>DB 인덱스와 B+ 트리 인덱스의 구조 및 장단점에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### DB 인덱스

- 테이블을 처음부터 끝까지 검색하지 않고 인덱스를 검색하여 해당 자료의 테이블을 엑세스 하는 방법
    - ex) DB를 책으로 비유하면 데이터는 책의 내용, 데이터가 저장된 레코드의 주소는 index 목록에 있는 페이지 번호
- 항상 정렬된 상태를 유지하기 때문에 원하는 값을 검색하는데 빠르지만, 새로운 값을 추가하거나 삭제, 수정하는 경우에는 쿼리문 실행 속도가 느려짐
- 즉, 인덱스는 데이터의 저장 성능을 희생하고 그대신 데이터의 검색 속도를 높이는 기능

### B-Tree

- 이진트리를 확장해 하나의 노드가 가질 수 있는 자식 노드의 최대 숫자가 2보다 큰 균형 트리
- 노드 안의 데이터는 오름차순으로 정렬

### B+ 트리

- 인덱스에 자주 사용되는 자료구조
- B-Tree를 개선시킨 자료구조
- 모든 노드에 키와 값이 함께 저장되는 B-Tree와 달리 중간 노드에는 키만 저장하고 리프 노드에 키와 값을 함께 저장해 리프 노드끼리 LinkedList로 연결하는 방식
- 검색할 때 B-Tree는 모든 노드를 확인해야 하지만, B+ Tree는 데이터가 담긴 리프 노드끼리 연결되어 있기 때문에 연결 리스트로 조회 가능
</div>
</ul>
</div>
</details>
<details>
<summary><strong>SQL Injection 방어 기법에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### SQL Injection

- 공격자가 악의적인 의도를 갖는 SQL 구문을 삽입하여 데이터베이스를 비정상적으로 조작하는 코드 인젝션 공격 기법

### 방어 기법

1. input 값을 받을 때, 특수문자 여부 검사하기
2. SQL 서버 오류 발생 시, 해당하는 에러 메시지 감추기
3. Prepared Statement 구문 사용
    - Java에서 SQL 문을 실행하기 위한 인터페이스 중 하나로, 보안과 성능을 개선하는 역할
    - 쿼리문에서 전달인자 값을 `?`로 받는 것
</div>
</ul>
</div>
</details>
<details>
<summary><strong>JOIN과 Inner Join, Outer Join의 차이에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### JOIN

- 두 개 이상의 테이블을 묶어 하나의 결과를 만드는 것
- 두 테이블을 결합하는 연산

<img width="500" alt="join" src="https://github.com/user-attachments/assets/0d7d4f4c-eb5d-4aac-b05a-2fd97940e095" width="90%" height="100%">

### Inner Join

- 서로 연관된 내용만 검색하는 조인 방법
- A와 B에 대해 수행하는 것은 **A와 B의 교집합**

### Outer Join

- 한 쪽에는 데이터가 있고 한 쪽에는 데이터가 없는 경우, 데이터가 있는 쪽의 내용을 전부 출력하는 방법
- A와 B에 대해 수행하는 것은 **A와 B의 합집합**
- LEFT OUTER JOIN, RIGHT OUTER JOIN, FULL OUTER JOIN
</div>
</ul>
</div>
</details>
<details>
<summary><strong>해시 인덱스 방식과 B+ 트리 인덱스 방식의 차이에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### 해시 인덱스 방식

- 컬럼의 값으로 생성된 해시를 기반으로 인덱스 구현
- 시간복잡도가 $O(1)$이라 검색이 매우 빠름
- 동등 연산(=)에 특화된 자료구조로, 부등호(<,>)와 같은 연속적인 데이터를 위한 순차 검색이 불가능하기 때문에 사용에 적합하지 않음
    - ex) “나는”으로 시작하는 모든 데이터 검색하기 위한 쿼리문의 경우 인덱스의 혜택을 받지 못함

### B+ 트리 인덱스 방식

- 중간 노드에는 키만 저장하고 리프 노드에 키와 값을 함께 저장해 리프 노드끼리 LinkedList로 연결하는 방식
- 데이터가 담긴 리프 노드끼리 연결되어 있기 때문에 연결 리스트로 조회가 가능하고 순차 검색이 용이
</div>
</ul>
</div>
</details>
<br>

### 💡 추가로 공부해 온 내용
<details>
<summary><strong>DELETE, TRUNCATE, DROP의 차이에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

![image](https://github.com/user-attachments/assets/79649387-5922-495a-b76d-397ab80ca297)

### DELETE

- 데이터는 지우지만 테이블 용량은 줄어들지 않고 원하는 데이터만 골라서 지우기 가능
- 비교적 처리 속도 느림
- 삭제 후 되돌릴 수 있음

### **TRUNCATE**

- 전체 데이터를 한번에 삭제하는 방식
- 테이블 용량이 줄어들고 인덱스 등도 삭제되지만 테이블은 삭제할 수 없음
- 삭제 후 되돌릴 수 없음

### **DROP**

- 테이블 자체를 완전히 삭제하는 방식(공간, 인덱스, 객체 모두 삭제)
- 삭제 후 되돌릴 수 없음
</div>
</ul>
</div>
</details>
