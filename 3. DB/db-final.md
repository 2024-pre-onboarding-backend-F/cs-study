## 3주차 주제 : 데이터베이스

### 🎨 공통 질문

1. **DB 인덱스와 B+ 트리 인덱스의 구조 및 장단점에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

DB 인덱스는 테이블을 처음부터 끝까지 검색하지 않고 인덱스를 검색하여 해당 자료의 테이블을 엑세스 하는 방법입니다.

인덱스는 항상 정렬된 상태를 유지하기 때문에 원하는 값을 검색하는데 빠르지만, 새로운 값을 추가하거나 삭제, 수정하는 경우에는 쿼리문 실행 속도가 느려집니다. 즉, 인덱스는 데이터의 저장 성능을 희생하고 그 대신 데이터의 검색 속도를 높이는 기능이라고 할 수 있습니다.

B+ 트리는 인덱스에 자주 사용되는 자료구조로, B-Tree를 개선시킨 자료구조입니다.

이때 B-Tree란 이진트리를 확장한 트리로, 하나의 노드가 가질 수 있는 자식 노드의 최대 숫자가 2보다 큰 균형 트리를 의미합니다. 노드 안의 데이터는 오름차순으로 정렬되어 있습니다.

B+ 트리는 모든 노드에 키와 값이 함께 저장되는 B-Tree와 달리 중간 노드에는 키만 저장하고 리프 노드에 키와 값을 함께 저장해 리프 노드끼리 LinkedList로 연결하는 방식입니다.

검색할 때 B-Tree는 모든 노드를 확인해야 하지만, B+ Tree는 데이터가 담긴 리프 노드끼리 연결되어 있기 때문에 연결 리스트로 조회할 수 있습니다.
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

2. **SQL Injection 방어 기법에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

SQL Injection은 공격자가 악의적인 의도를 갖는 SQL 구문을 삽입하여 데이터베이스를 비정상적으로 조작하는 코드 인젝션 공격 기법입니다.

SQL Injection 방어 기법으로는 input 값을 받을 때 특수문자 여부 검사하기, SQL 서버 오류 발생 시 해당하는 에러 메시지 감추기, Prepared Statement 구문 사용하기 등이 있습니다.
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

3. **JOIN과 Inner Join, Outer Join의 차이에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

JOIN은 두 개 이상의 테이블을 묶어 하나의 결과를 만드는 것으로, 두 테이블을 결합하는 연산을 의미합니다. 이 JOIN에는 크게 Inner Join과 Outer Join이 있습니다.

Inner Join은 서로 연관된 내용만 검색하는 조인 방법입니다.

Outer Join은 한 쪽에는 데이터가 있고 한 쪽에는 데이터가 없는 경우, 데이터가 있는 쪽의 내용을 전부 출력하는 방법입니다. Outer Join에는 LEFT OUTER JOIN, RIGHT OUTER JOIN, FULL OUTER JOIN 등이 있습니다.
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

4. **해시 인덱스 방식과 B+ 트리 인덱스 방식의 차이에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

해시 인덱스 방식은 컬럼의 값으로 생성된 해시를 기반으로 인덱스를 구현하는 방식입니다. 동등 연산(=)에 특화된 자료구조로, 부등호(<,>)와 같은 연속적인 데이터를 위한 순차 검색이 불가능하기 때문에 사용에 적합하지 않습니다.

B+ 트리 인덱스 방식은 중간 노드에는 키만 저장하고 리프 노드에 키와 값을 함께 저장해 리프 노드끼리 LinkedList로 연결하는 방식입니다. 데이터가 담긴 리프 노드끼리 연결되어 있기 때문에 연결 리스트로 조회가 가능하고 순차 검색이 용이하다는 장점이 있습니다.
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
1. **DELETE, TRUNCATE, DROP의 차이에 대해 설명해주세요.**

<details>
  <summary>이지원</summary>

DELETE는 데이터는 지우지만 테이블 용량은 줄어들지 않고 원하는 데이터만 골라서 지울 수 있습니다. 비교적 처리 속도는 느리고, 삭제 후 되돌릴 수 있습니다.

TRUNCATE은 전체 데이터를 한번에 삭제하는 방식으로, 테이블 용량이 줄어들고 인덱스 등도 삭제되지만 테이블은 삭제할 수 없습니다. 삭제 후 되돌릴 수 없습니다.

DROP은 테이블 자체를 완전히 삭제하는 방식으로, 공간, 인덱스, 객체 모두 삭제됩니다. 삭제 후 되돌릴 수 없습니다.
</details>

</br>

### 💫 공부한 내용 정리한 링크
| 이름 | 블로그 링크 |
|------|--------------|
|김영주||
|이지원|<a href="DB_jiwon_1115.md" target="_blank">github md파일</a>|
|정은경||
|정진희||
