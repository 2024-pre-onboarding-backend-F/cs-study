# 2주차 : 알고리즘 (이지원)

### 🎨 첫번째 공통 질문
<details>
<summary><strong>동적 계획법(DP, Dynamic Programming)에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

- 동적 계획법 : 주어진 문제를 풀기 위해, 문제를 여러 개의 하위 문제로 나누어 푸는 방법
- 어떤 부분 문제가 다른 문제들을 해결하는데 사용될 수 있어, 답을 여러 번 계산하는 대신 한 번만 계산하고 그 결과를 재활용하는 **메모이제이션(Memoization)**기법으로 속도를 향상시킬 수 있음

### 사용 조건

1. **Overlapping Subproblems(겹치는 부분 문제)**

    - 동일한 작은 문제들이 반복하여 나타나는 경우에 사용이 가능
    
2. **Optimal Substructure(최적 부분 구조)**
    - 부분 문제의 최적 결과 값을 사용해 전체 문제의 최적 결과를 낼 수 있는 경우 ➡️ 특정 문제의 정답은 문제의 크기에 상관없이 항상 동일

### 두 가지 접근 방법

1. Bottom - up

    - 부분 문제에서부터 문제를 해결하여 점차 큰 문제를 풀어가는 방식
    - for 문을 이용하는 방식
2. Top - down
    - 큰 문제에서 부분 문제로 쪼개가면서 문제를 푸는 방법
    - 재귀를 이용하는 방식

### 예시 - 피보나치 수열

- 피보나치 수열 : 이전 두 항의 합으로 이루어지는 수열
    
    ```jsx
    function fibonacci(n) {
      // 🌟 메모이제이션 🌟
      // 피보나치 수열을 저장할 배열
      const dp = new Array(n + 1);
    
      // 초기값 설정
      dp[0] = 0;
      dp[1] = 1;
    
      // 🌟 점화식 🌟
      // 피보나치 수열 계산
      for (let i = 2; i <= n; i++) {
        dp[i] = dp[i - 1] + dp[i - 2];
      }
    
      // 결과 반환
      return dp[n];
    }
    
    // 예시로 n = 10일 때 피보나치 수열 값 출력
    console.log(fibonacci(10));  // Output: 55
    ```

</div>
</ul>
</div>
</details>
<details>
<summary><strong>퀵 정렬(Quick Sort)에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### 퀵 정렬(Quick Sort)

- 빠른 정렬 속도를 자랑하는 분할 정복 알고리즘 중 하나
- 피봇을 설정하고 피봇보다 큰 값과 작은 값으로 분할하여 정렬
</div>
</ul>
</div>
</details>
<details>
<summary><strong>Big-O 표기법의 시간 복잡도 크기 순서를 말해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

**시간 복잡도** : 알고리즘의 실행 속도

- **Big-O 표기법**(`O(N)`) : 알고리즘 **최악**의 실행시간
- **Ω 표기법**(`Ω(N)`) : 알고리즘 **최상**의 실행시간
- **Θ 표기법**(`Θ(N)`) : 알고리즘 **평균** 실행시간

### 크기 순서

- $O(1) < O(log N) < O(N) < O(NlogN) < O(N^2) < O(2^N) < O(N!)$

  <img width="400" alt="시간 복잡도" src="https://github.com/user-attachments/assets/f1c712d0-60cb-4cb8-8b74-f35f2942d708" width="90%" height="100%">

</div>
</ul>
</div>
</details>
<details>
<summary><strong>재귀 알고리즘에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### 재귀 알고리즘

- 함수 내부에서 함수가 자기 자신을 또 다시 호출하여 문제를 해결하는 알고리즘

    ![image](https://github.com/user-attachments/assets/ff31d664-5e83-40b9-b7bd-03353cc505a4)
    
- 무한루프에 빠지지 않도록 종료 조건을 명확하게 설정해주어야 함

### 예시 - 팩토리얼 계산

- 팩토리얼 : 자연수 n에 대해서 1부터 n까지의 모든 자연수를 곱한 값
- `factorial()` 함수 - 파라미터로 값을 넘길 경우 재귀함수로 반복하여 결괏값을 반환해 주는 함수
- 5라는 값을 파라미터로 넘겼을 경우
    
    ```
    factorial(5) = 5 * factorial(4)
    factorial(4) = 4 * factorial(3)
    factorial(3) = 3 * factorial(2)
    factorial(2) = 2 * factorial(1)
    factorial(1) = 1 * factorial(0)
    factorial(0) = 1
    ```
    
- Java 코드로 작성
    
    ```java
    public class Main {
        public static void main(String[] args) {
            System.out.println(factorial(5)); // 5! = 5 * 4 * 3 * 2 * 1 = 120
        }
     
        public static int factorial(int n) {
            if (n == 0) { // 기본 케이스
                return 1;
            } else { // 재귀 케이스
                return n * factorial(n - 1);
            }
        }
    }
    ```
    
</div>
</ul>
</div>
</details>
<br>

### 🎨 두번째 공통 질문
<details>
<summary><strong>선택 정렬(Selection Sort)에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### 선택 정렬(Selection Sort)

- 가장 작은 데이터를 찾아 가장 앞의 데이터와 교환해나가는 방식
- 최선, 평균, 최악의 경우 시간 복잡도는 $O(N^2)$

### 과정

1. 주어진 리스트 중 최소값 찾음
2. 그 값을 맨 앞에 위치한 값과 교체
3. 맨 처음 위치를 뺀 나머지 리스트를 같은 방법으로 교체

### 예시

![image](https://github.com/user-attachments/assets/a6a638e2-b2c8-42fd-bed5-ef13da8ae739)

</div>
</ul>
</div>
</details>
<details>
<summary><strong>삽입 정렬(Injection Sort)에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### 삽입 정렬(Injection Sort)

- 두 번째 값부터 시작해 그 앞에 존재하는 원소들과 비교하여 위치 지정하는 방식
- 최선의 경우 시간 복잡도는 $O(N)$, 평균, 최악의 경우 시간 복잡도는 $O(N^2)$

### 예시

![image](https://github.com/user-attachments/assets/140cd90c-6340-449e-8c4b-c5f2b63c124e)

</div>
</ul>
</div>
</details>
<details>
<summary><strong>병합 정렬(Merge Sort)에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### 병합 정렬(Merge Sort)

- 하나의 리스트를 두 개의 리스트로 분할한 다음 각각의 분할된 리스트를 정렬한 후에 합해서 정렬된 하나의 리스트로 만드는 정렬 알고리즘
- 최선, 평균, 최악의 경우 시간 복잡도는 $O(NlogN)$

### 과정

1. **분할(Divide)** : 리스트를 두 개의 리스트로 분할
2. **정복(Conquer)** : 분할된 리스트를 정렬
3. **결합(Combine)** : 정렬된 두 개의 리스트를 하나의 정렬된 리스트로 결합

### 예시

![image](https://github.com/user-attachments/assets/9ce1b205-fa8d-497f-9224-1d6406ab78a7)

- 부분 리스트의 사이즈가 1이 될 때까지 분할
- 정렬 시 한번에 결합하는게 아니라 분할과 동일한 크기로 부분 리스트 결합
</div>
</ul>
</div>
</details>
<details>
<summary><strong>허프만 코딩에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### 허프만 코딩

- 데이터 문자의 빈도 수를 가지고 압축하는 과정
- **접두부 코드**와 **최적 코드** 사용
    - 접두부 코드 : 각 문자에 부여된 이진 코드가 다른 이진 코드의 접두부가 되지 않는 코드 (즉, 겹치지 않도록 이진 코드를 만드는 것)
    - 최적 코드 : 인코딩된 메시지의 길이가 가장 짧은 코드

### 접두부 코드

> **접두부 코드가 아닌 예**
> 
> 
> a : 01
> 
> b : 101
> 
> c : 010
>

- 위에서 `01`은 `010`의 접두부이기 때문에 접두부 코드가 아님

- 인코딩된 코드 010이 c를 인코딩한 것인지 아니면 a와 다른 문자를 인코딩한 것인지 알 수 없는 문제

> **접두부 코드인 예**
> 
> 
> a : 01
> 
> b : 10
> 
> c : 111
>
</div>
</ul>
</div>
</details>
