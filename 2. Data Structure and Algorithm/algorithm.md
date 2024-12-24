## 2주차 주제 : 알고리즘

### 🎨 공통 질문 

1. **동적 계획법(DP, Dynamic Programming)에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>
  
  동적 계획법이란 주어진 문제를 풀기 위해 문제를 여러 개의 하위 문제로 나누어 푸는 방법을 의미합니다.

  어떤 부분 문제가 다른 문제들을 해결하는데 사용될 수 있어, 답을 여러 번 계산하는 대신 한 번만 계산하고 그 결과를 재활용하는 메모이제이션(Memoization)기법으로 속도를 향상시킬 수 있습니다.
</details>

<details>
  <summary>정은경</summary>
  동적계획법은 복잡한 문제를 더 작은 하위 문제로 나누어 해결하는 알고리즘 설계 기법입니다.
  즉, 상향식 방법으로 작은 하위 문제들부터 시작해 그 결과를 저장하고, 이를 사용해 점진적으로 큰 문제를 해결하는 방법입니다. 
  대표적인 방식으로는 메모이제이션이 있으며, 이를 통해 중복 계산을 중리고 효율적인 시간 복잡도를 가질 수 있습니다.
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

2. **퀵 정렬(Quick Sort)에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>
  퀵 정렬은 빠른 정렬 속도를 자랑하는 분할 정복 알고리즘 중 하나로, 피봇을 설정하고 피봇보다 큰 값과 작은 값으로 분할하여 정렬하는 방법입니다.
</details>

<details>
  <summary>정은경</summary>
  빠른 수행 속도를 자랑하는 비교 정렬 알고리즘입니다. 피봇을 설정하고 피봇보다 큰 값과 작은 값으로 분할하여 정렬합니다.
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

3. **Big-O 표기법의 시간 복잡도 크기 순서를 말해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>
  
  시간 복잡도는 알고리즘의 실행 속도를 의미합니다.

  Big-O 표기법의 시간 복잡도 크기 순서는 $O(1) < O(log N) < O(N) < O(NlogN) < O(N^2) < O(2^N) < O(N!)$입니다.
</details>

<details>
  <summary>정은경</summary>
  시간 복잡도는 코드의 실행시간을 의미합니다.

  Big-O 표기법의 시간 복잡도 크기 순서는 O(1) < O(log N) < O(N) < O(NlogN) < O(N^2) < O (N^3) < O(2^N) 입니다.

  * 상수시간 < 로그 시간 < 선형 시간< 선형 로그 시간 < 2차 시간 < 3차 시간 < 지수 시간
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

4. **재귀 알고리즘에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

  재귀 알고리즘은 함수 내부에서 함수가 자기 자신을 또 다시 호출하여 문제를 해결하는 알고리즘을 말합니다.

  재귀 알고리즘의 경우 무한루프에 빠지지 않도록 종료 조건을 명확하게 설정해주어야 합니다.
</details>

<details>
  <summary>정은경</summary>
  재귀 알고리즘은 함수가 자기 자신을 호출하여 문제를 해결하는 알고리즘 설계방식입니다. 
  재귀함수는 기본적으로 무한 루프를 방지하는 종료 조건과 문제를 더 작은 문제로 나누고 자신을 호출하여 작업하는 재귀 단계로 구성됩니다.
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

5. **선택 정렬(Selection Sort)에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

  선택 정렬은 가장 작은 데이터를 찾아 가장 앞의 데이터와 교환해나가는 방식으로, 시간 복잡도는 $O(N^2)$입니다.
</details>

<details>
  <summary>정은경</summary>
  선택 정렬은 정렬되지 않은 배열에서 가장 작은, 혹은 가장 큰 값을 선택하여 정렬된 부분에 하나씩 추가하는 방식으로 작동하는 정렬 알고리즘입니다.
  동작 원리는 주어진 배열에서 최솟값 또는 최댓값을 찾아 해다 값을 배열의 맨 앞 요소와 교환하고, 이 과정을 반복합니다.
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

6. **삽입 정렬(Injection Sort)에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

  삽입 정렬은 두 번째 값부터 시작해 그 앞에 존재하는 원소들과 비교하여 위치를 지정하는 방식입니다.

  최선의 경우 시간 복잡도는 $O(N)$이고, 평균, 최악의 경우 시간 복잡도는 $O(N^2)$입니다.
</details>

<details>
  <summary>정은경</summary>
  삽입정렬은 각 요소를 이미 정렬된 부분에 삽입하는 방식으로 작동되는 정렬 알고리즘입니다.
  삽입정렬의 작동 원리는 배열의 두 번째 요소부터 시작해, 해당 요소를 이전의 정렬된 부분과 비교하고 적절한 위치를 찾아 삽입합니다.
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

7. **병합 정렬(Merge Sort)에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

  병합 정렬은 하나의 리스트를 두 개의 리스트로 분할한 다음 각각의 분할된 리스트를 정렬한 후에 합해서 정렬된 하나의 리스트로 만드는 정렬 알고리즘입니다.

  시간 복잡도는 $O(NlogN)$입니다.
</details>

<details>
  <summary>정은경</summary>
  병합정렬은 배열을 두 개의 균등한 크기로 분할하고, 각각을 정렬한 후 병합하여 최종적으로 정렬된 배열을 만드는 방식으로 작동합니다.
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

8. **허프만 코딩에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>

  허프만 코딩은 데이터 문자의 빈도 수를 가지고 압축하는 과정을 의미합니다.

  주로 접두부 코드와 최적 코드를 사용합니다. 이때 접두부 코드란, 각 문자에 부여된 이진 코드가 다른 이진 코드의 접두부가 되지 않는 코드를 의미합니다.
</details>

<details>
  <summary>정은경</summary>
  허프만 코딩은 주어진 데이터에서 각 문자의 빈도수를 기반으로 가변 길이의 접두사 코드를 생성하는 데이터 압축 알고리즘입니다.
  빈도가 높은 문자는 짧은 코드로, 빈도가 낮은 문자는 긴 코드로 표현하여 전제 데이터 크기를 최소화합니다.

  > 접두사 코드: 어떤 코드도 다른 코드의 접두사가 되지 않아, 디코딩 시 혼란인 없다
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
|이지원|<a href="algorithm_jiwon.md" target="_blank">github md파일</a>||
|정은경|<a href="https://velog.io/@jeg1124/series/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98" target="_blank">블로그 링크</a>|
|정진희||
