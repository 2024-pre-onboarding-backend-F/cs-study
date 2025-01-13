## 5주차 주제 : 자바

### 🎨 공통 질문

1. **Java의 장단점에 대해 설명해주세요**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>정은경</summary>
  자바의 가장 큰 장점은 플랫폼 독립성과 객체 지향 설계입니다. 강력한 표준 라이브러리와 자동 메모리 관리로 개발 생산성이 뛰어나며,  보안성과 멀티스레드 기능을 지원해 확장성이 높은 애플리케이션 개발이 가능합니다.

  하지만 네이티브 언어(C, C++)와 비교하면 JVM 기반의 실행으로 상대적으로 실행 속도가 느립니다. JVM과 가비지 컬렉션 동작이 메모리를 많이 소비할 수 있다는 점이 단점입니다. 그리고 최신 언어에 비해 문법적으로 코드가 길어질 수도 있습니다. 
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

2. **Java에서, ==와 equals의 차이는 무엇인지 알고 계시나요?**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>정은경</summary>
  `==`는 두 객체의 참조값(메모리주소)를 비교합니다. 두 객체가 동일한 주소를 참조할 때만 true를 반환합니다.

  equals는 객체가 의미적으로 동일한 값을 가지는지 비교합니다. 

  equals는 ==와 동일하게 동작하지만, String, Integer와 같은 클래스에서는 재정의되어 값비교를 수행합니다.
  * class 타입을 선언했을 때는 서로간의 주소값이 달라 단순히 ==만 사용하면 사용자가 원하는 결과를 얻지 못할 수도 있습니다.
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

3. **try-catch-finally의 단점과 이로 인해 나온 구문에 대해 알고 계신다면 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>정은경</summary>
  중첩된 try-catch 블록은 코드가 복잡하고 읽기 어려워 코드의 가독성이 저하됩니다. 여러 메서드에서 동일한 예외 처리가 반복됩니다. 예외가 발생했을 때 자원을 해제하는 코드가 누락되거나 잘못 작성되면 자원 누수가 발생할 수도 있습니다.

  이로 인해 try-with-resources는 java7부터 도입된 구문으로,  자원의 자동 해제(Auto-closeable)를 지원합니다. 더불어, 예외 처리 코드가 간결해져 가독성이 향상되었고 자원 해제 누락 위험이 줄어들어 안전하게 자원을 관리할 수 있습니다.
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

4. **stream API에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>정은경</summary>
  Java 8에서 추가된 기능으로, 컬렉션 또는 배열의 데이터 처리를 함수형 프로그래밍 방식으로 수행하는 데 사용됩니다. 중간 연산은 필요할 때 실행되며, 최종 연산이 호출되어야 처리 과정이 시작됩니다.
  병렬 처리를 지원해 멀티코어 CPU를 활용하여 성능을 향상시킬 수 있습니다. 

  대규모 데이터 처리의 성능 향상, 다양한 중간 및 최종 연산을 통한 데이터 필터링과 변환이 가능합니다.
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

5. **JVM이 무엇인지 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>정은경</summary>
  JVM은 Java 프로그램을 실행하기 위한 가상 실행 환경입니다. 컴파일 된 바이트 코드를 기계가 이해할 수 있는 기계어로 변환해 줍니다. 
  Heap, Stack 등 메모리 구조를 관리하고, 가비지 컬렉션을 실행해 사용되지 않는 객체를 자동으로 메모리에서 제거합니다.
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

6. **Garbage Collector가 무엇인지, 어떻게 동작하는지 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>정은경</summary>
  가비지 컬렉터는 JVM의 메모리 관리르 자동화하는 역할을 합니다.

  동작 방식은 객체를 표시(mark)하고, 참조되지 않는 객체를 제거(sweep)합니다. JVM의 Heap 부분은 Young/Old 2가지 영역으로 설계됩니다. Young 부분은 새로 생성된 객체, Old는 오래 살아남은 객체입니다.
  Old 영역이 Young 영역보다 크게 할당되는 이유는 Young 영역의 수명이 짧은 객체들은 큰 공간을 필요하지 않으므로, 큰 객체들은 바로 Old 영역 할당합니다.
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

7. **추상 클래스와 인터페이스에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>정은경</summary>
  추상 클래스의 일부 메서드는 구현하고, 일부는 추상 메서드로 선언합니다. 상속 관계를 형성하며, 기본 구현을 제공하면서 확장을 허용하는 특징이 있습니다. 다만, 다중 상속은 불가능합니다.

  인터페이스의 모든 메서드는 기본적으로 추상 메서드이며, Java8이후 default 메서드와 satic 메서드를 가질 수 있습니다. 다중 구현을 통해 클래스 간의 공통 기능을 정의합니다.
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>

8. **Error와 Exception의 차이에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>정은경</summary>
  Error는 프로그램이 복구할 수 없는 심각한 문제를 의미합니다. 예로는 OutOfMemoryError, StackOverflowError가 있습니다. 

  Exception은 프로그램에서 발생할 수 있는 일반적인 문제로, 복구 가능성이 있습니다. 예로는 IOException, NullPointerException이 있습니다.
</details>

<details>
  <summary>정진희</summary>
  <!-- 내용 -->
</details>

</br>  

9. **Java에서 MultiThread 프로그래밍에 대해 설명해주세요.**

<details>
  <summary>김영주</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>이지원</summary>
  <!-- 내용 -->
</details>

<details>
  <summary>정은경</summary>
  Java에서 멀티스레드 프로그래밍은 병렬 처리를 통해 작업의 효율성을 높이고, 응답성을 개선하기 위해 사용됩니다.
  구현 방법은 Thread 클래스를 상속하거나 Runnable 인터페이스로 구현하는 방법이 있습니다.

  멀티스레드 프로그래밍에서 중요한 점은 효율적인 동시성 관리와 데드락 방지 설계입니다.
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
|이지원||
|정은경|<a href="https://velog.io/@jeg1124/series/JAVA" target="_blank">블로그 링크</a>|
|정진희||
