# 5주차 : 자바 (이지원)

### 🎨 첫번째 공통 질문
<details>
<summary><strong>JVM이 무엇인지 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### JVM

- Java Virtual Machine, 자바 가상 머신
- OS와 Java Application 사이를 중재해주는 가상 머신
- 자바 애플리케이션을 클래스 로더를 통해 읽어 자바 API와 함께 실행하는 역할

### JVM 동작 방식

<img width="450" alt="JVM" src="https://github.com/user-attachments/assets/1ba12797-d52f-4c4d-9f21-7ca6cf84e772" width="90%" height="100%">

1. 자바 프로그램을 실행하면 JVM은 OS로부터 메모리 할당받음
2. 자바 컴파일러(javac)가 자바 소스코드(.java)를 자바 바이트 코드(.class)로 컴파일
3. Class Loader는 동적 로딩을 통해 필요한 클래스들을 로딩 및 링크하여 Runtime Data Area에 올림
4. Runtime Data Area에 로딩된 바이트 코드는 Execution Engine을 통해 해석됨
5. 이 과정에서 Execution Engine에 의해 Garbage Collector의 작동과 쓰레드 동기화가 이루어짐

### JVM 구조

<img width="450" alt="JVM" src="https://github.com/user-attachments/assets/cf8fe0f3-b581-4973-ae45-e45bd0f606ce" width="90%" height="100%">

### 클래스 로더 (Class Loader)

- JVM 내로 클래스 파일을 동적으로 로드하고, 링크를 통해 배치하는 작업을 수행하는 모듈
- 로드된 바이트 코드(.class)들을 엮어서 JVM의 메모리 영역인 Runtime Data Areas에 배치

### 실행 엔진 (Execution Engine)

- 클래스 로더를 통해 런타임 데이터 영역에 배치된 바이트 코드를 명령어 단위로 읽어서 실행
- 바이트 코드는 가상 머신이 이해할 수 있는 중간 레벨로 컴파일된 코드 → 실행 엔진은 이와 같은 바이트 코드를 실제로 JVM 내부에서 기계가 실행할 수 있는 형태로 변경
- 수행 과정에서 인터프리터와 JIT 컴파일러 두 가지 방식 혼합하여 바이트 코드 실행
    - 인터프리터(Interpreter) : 바이트 코드 명령어를 하나씩 읽어서 해석하고 바로 실행
    - JIT 컴파일러(Just-In-Time Compiler) : 인터프리터 단점을 보완하기 위해 도입된 방식, 바이트 코드 전체를 컴파일하여 Native Code로 변경하고 이후 네이티브 코드로 직접 실행하는 방식
    
    > Native Code : JAVA에서 부모가 되는 C언어나, C++, 어셈블리어로 구성된 코드
    > 

### 런타임 데이터 영역 (Runtime Data Area)

- JVM 메모리 영역으로, 자바 애플리케이션을 실행할 때 사용되는 데이터들을 적재하는 영역

<img width="450" alt="JVM 메모리 영역" src="https://github.com/user-attachments/assets/30b4f5b3-6cc0-4cbc-afd1-71e109661a78" width="90%" height="100%">

- Method Area, Heap Area, Stack Area, PC Register, Native Method Stack
</div>
</ul>
</div>
</details>
<details>
<summary><strong>Garbage Collector가 무엇인지, 어떻게 동작하는지 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### Garbage Collection

- JVM의 **Heap 영역**에서 동적으로 할당했던 메모리 중 필요 없게 된 메모리 객체(garbage)를 모아 주기적으로 제거하는 프로세스

### GC 대상

- 특정 객체가 garbage인지아닌지 판단하기 위해 **도달성, 도달능력(Reachability)**라는 개념 적용
- Reachable : 객체가 참조되고 있는 상태
- Unreachable : 객체가 참조되고 있지 않은 상태 **(GC 대상)**
    
    > ex. JVM 메모리에서 객체들은 실질적으로 Heap 영역에서 생성되고 Method Area나 Stack Area에서는 Heap Area에 생성된 객체의 주소만 참조하는 형식으로 구성
    >
    > <img width="450" alt="참조 형식" src="https://github.com/user-attachments/assets/3d9eb490-6c72-41e6-bf49-bbb442adfd95" width="90%" height="100%">
    >
    > 이렇게 생성된 Heap Area 객체의 메모리 주소를 가지고 있는 참조 변수가 삭제되는 현상이 발생하면(그림에서 빨간색 객체), Heap 영역에서 어디서든 참조되고 있지 않은 객체 발생
    > 
    > ⇒ 이러한 객체들을 주기적으로 Garbage Collector가 제거
    > 

### 청소 방식

- Mark And Sweep : 다양한 GC에서 사용되는 객체를 솎아내는 내부 알고리즘
- 가비지 컬렉션이 될 대상 객체를 식별(Mark)하고 제거(Sweep)하며 객체가 제거되어 파편화된 메모리 영역을 앞에서부터 채워나가는 작업(Compaction) 수행
    - 가비지 컬렉터 종류에 따라 Compaction 과정 하지 않는 경우도 있음

### 동작 과정

- Heap 영역 : 동적으로 레퍼런스 데이터가 저장되는 공간, 가비지 컬렉션 대상이 되는 공간
    
    > Heap 영역은 **객체는 대부분 일회성이며, 메모리에 오랫동안 남아있는 경우는 드물다**는 전제로 설계 ⇒ Heap 영역을 Young과 Old 2가지 영역으로 설계
    > 
    - Young 영역 : 새롭게 생성된 객체가 할당되는 영역
        - 3가지 영역인 Eden, Survivor 0, Survivor 1로 나누어짐
        - Young 영역에 대한 가비지 컬렉션 → Minor GC
    - Old 영역 : Young 영역에서 Reachable 상태를 유지하여 살아남은 객체가 복사되는 영역
        - Young 영역보다 크게 할당되며, 영역 크기가 큰 만큼 가비지 적게 발생
        - Old 영역에 대한 가비지 컬렉션 → Major GC, Full GC
</div>
</ul>
</div>
</details>
<details>
<summary><strong>추상 클래스와 인터페이스에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### 추상 클래스

- `abstract` 키워드를 사용해 선언한 클래스
- 추상 메소드를 최소 한 개 이상 포함한 클래스
    - 추상 메소드 : 메서드의 선언부만 작성하고 구현부는 미완성인 채로 남겨둔 메소드
- 추상 메소드 외에 일반클래스와 같이 일반적인 필드, 메서드, 생성자를 가질 수 있음
- 주 목적은 관련성이 높은 클래스 간의 코드를 공유하고 확장하고 싶은 목적 - 클래스 간의 연관 관계를 구축하는 것에 초점

### 인터페이스

- `interface` 키워드를 사용해 선언
- `default`와 `static`을 제외하고는 **추상 메소드와 상수만을 포함**
    - 인터페이스 내부 모든 메소드는 추상 메소드로, abstract public이 생략되어 있는 상태
    - 상수 필드는 public static final이 생략되어 있는 상태
- 다중 상속이 가능
- 주 목적은 관련성이 없는 클래스들이 논리적으로 같은 기능을 자신에 맞게 구현을 강제하는데에 목적

### 공통점

- 추상 메소드를 가지고 있어야 함
- 인스턴스화 할 수 없음 (new 생성자 사용 불가)
- 인터페이스 또는 추상 클래스를 사용하기 위해서는 하위 클래스에서 확장/구현해야 함

### 차이점

|  | 추상 클래스 | 인터페이스 |
| --- | --- | --- |
| 사용 키워드 | abstract | interface |
| 사용 가능 변수 | 제한 없음 | static final (상수) |
| 사용 가능 접근 제어자 | 제한 없음 (public, private, protected, default) | public |
| 사용 가능 메소드 | 제한 없음 | abstract, default, static, private |
| 상속 키워드 | extends | implements |
| 다중 상속 가능 여부 | 불가능 | 가능 |

</div>
</ul>
</div>
</details>
<details>
<summary><strong>Error와 Exception의 차이에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### 오류 (Error)

- 실행 중 일어날 수 있는 치명적 오류
- 런타임 시점에 발생하며, 컴파일 시점에서 알 수 없음
- 오류 발생 시 프로그램은 비정상적으로 종료
- 예측 불가능한 UnChecked Type

### 예외 (Exception)

- Error보다 비교적 경미한 오류
- Checked Exception은 컴파일 시점에, Unchcked Exception은 런타임 시점에 알 수 있음
- try-catch를 이용해 프로그램의 비정상적인 종료 예방 가능
- Checked Type, Unchecked Type으로 분류
    - Checked Type - IOException, ClassNotFoundException 등
    - Unchecked Type - NullPointerException, ArrayIndexOutOfBoundException 등
</div>
</ul>
</div>
</details>
<details>
<summary><strong>Java에서의 MultiThread 프로그래밍에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### 멀티스레드 생성 방법

- 방법 1: Thread 클래스를 상속받아서 run을 오버라이드해서 정의
- 방법 2: Runnable 인터페이스를 구현하여 Thread 생성자에 인자로 넘김
- 방법 3: Callable 인터페이스를 구현하여 FutureTask에 한번 감싸서 Thread의 인자로 넘김
- **Runnable은 Exception이 없고 리턴값도 없으나 Callable은 리턴값이 있고 Exception을 발생시킬 수 있음**

### 멀티스레드 실행 방법

- 보통 start() 메서드를 사용해서 호출하는데 start 한다고 해서 바로 실행되는 것은 아니고 실행 대기열에 저장된 후 차례가 오면 실행
- 정확하게 말하자면, start는 새로운 스레드가 작업을 실행하는데 필요한 새로운 호출 스택을 생성해서 그곳에 run 메서드를 올려둠 → 이후 그곳에서 run 메서드를 호출하고 스레드가 별개의 작업을 수행
</div>
</ul>
</div>
</details>

### 💡 첫번째 추가로 공부해 온 내용
<details>
<summary><strong>JVM의 메모리(Runtime Data Area)구조에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

<img width="450" alt="JVM 메모리 영역" src="https://github.com/user-attachments/assets/30b4f5b3-6cc0-4cbc-afd1-71e109661a78" width="90%" height="100%">

### 메서드 영역 (Method Area)

- JVM이 시작될 때 생성되는 공간
- 바이트 코드(.class)를 처음 메모리 공간에 올릴 때 초기화되는 대상을 저장하기 위한 메모리 공간
- JVM이 동작하고 클래스가 로드될 때 적재되서 프로그램이 종료될 때까지 저장됨
- 클래스와 인터페이스, 메서드, 필드, static 변수, final 변수 등이 저장되는 영역
- Runtime Constant Pool : 메서드 영역에 존재하는 별도의 관리 영역, 상수 자료형을 저장하여 참조하고 중복을 막는 역할

### 힙 영역 (Heap Area)

- 런타임 시 동적으로 할당하여 사용하는 영역
- new 연산자로 생성되는 클래스, 인스턴스, 배열 타입 등이 저장되는 곳
- 가비지 컬렉션 대상이 되는 공간

### 스택 영역 (Stack Area)

- 임시적으로 사용되는 변수나 정보들이 저장되는 영역
- 매개변수, 지역변수, 연산 시 발생하는 값들 임시로 저장
- 매서드 호출 시마다 개별적으로 스택 생성

### PC 레지스터 (Program Counter Register)

- 현재 수행 중인 JVM 명령어 주소 저장하는 공간

### 네이티브 메서드 스택 (Native Method Stack)

- 실제 실행할 수 있는 기계어로 작성된 프로그램을 실행시키는 영역
- 자바 이외의 언어(C, C++, 어셈블리 등)로 작성된 네이티브 코드 실행하기 위한 공간

> Method Area, Heap Area는 모든 쓰레드가 공유하는 영역
> 
> 
> Stack Area, PC Register, Native Method Stack은 각 쓰레드마다 생성되는 개별 영역
>
</div>
</ul>
</div>
</details>
<br>

### 🎨 두번째 공통 질문
<details>
<summary><strong>Java의 장단점에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### Java

- 객체지향 프로그래밍 언어
- 기본 자료형을 제외한 모든 요소들이 객체로 표현되고, 객체 지향 개념의 특징인 캡슐화, 상속, 다형성이 잘 적용된 언어

### 장점

- JVM에서 동작하기 때문에 특정 운영체제에 종속되지 않고, 독립적으로 실행될 수 있음
- 객체지향 언어로 객체지향 프로그래밍 가능
- JVM에서 가비지 컬렉션이 일어나기 때문에 별도의 메모리 관리가 필요 없고 비즈니스 로직에 집중할 수 있음
- 동적 로딩을 지원하기 때문에 각 객체가 필요한 시점에 클래스 생성

### 단점

- JVM에 의해 기계어로 번역되고 실행하는 과정을 거치기 때문에 비교적 느린 속도
</div>
</ul>
</div>
</details>
<details>
<summary><strong>Java에서, ==와 equals의 차이는 무엇인지 알고 계시나요?</strong></summary>
<div markdown="1">
<ul>
<div>

### == 연산자

- 참조 비교
- 두 객체가 같은 메모리 공간을 가리키는지 확인하는 연산

### **equals**

- 두 객체의 내부 값이 같은지 내용을 비교
- 객체 비교 시 Override해서 원하는 방식으로 수정
- 문자열 비교를 위해 사용하는 `equals()`의 경우 String 클래스에서 오버라이딩 하여 사용

```java
public class Main {
    public static void main(String[] args) {
    
    String str1 = "test";
		String str2 = "test";
		String str3 = new String("test");
		String str4 = new String("test");
		
		System.out.println(str1==str2); //true
		System.out.println(str1==str3); //false
		System.out.println(str1.equals(str3)); //true
    }
}
```

> 리터럴 사용하는 경우 Java Heap 메모리의 String Constant Pool이라는 영역에 같은 값의 문자열을 공유하여 메모리 사용량을 최적화하기 때문에 str1과 str2는 같은 주소값
> 
> 
> new 연산자를 사용하는 경우 Heap 영역에 저장되어 각각 다른 주소값을 할당받기 때문에 str3과 str4는 다른 주소값
>
</div>
</ul>
</div>
</details>
<details>
<summary><strong>try-catch-finally의 단점과, 이로 인해 나온 구문에 대해 알고 계신다면 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### **try-catch-finally 단점**

- 자원을 해제할 때 항상 메서드 끝에 finally를 붙여야 하기 때문에 코드가 복잡해지고 finally 문을 누락해 실수 가능성이 있음

### ➡️ try-with-resources

- try에 자원을 할당한 후 try문이 끝나면 알아서 자원 해제
- try 옆에 괄호로 리소스를 생성해주면, 따로 반납 코드 작성하지 않아도 자동으로 리소스 반납

```java
public static void main(String args[]) throws IOException {
    try (FileInputStream is = new FileInputStream("file.txt"); BufferedInputStream bis = new BufferedInputStream(is)) {
        int data;
        while ((data = bis.read()) != -1) {
            System.out.print((char) data);
        }
    }
}
```

</div>
</ul>
</div>
</details>
<details>
<summary><strong>Java의 Stream API에 대해 알고 계시나요? 안다면 아는대로 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### **Stream API**

- 일련의 데이터의 흐름을 표준화된 방법으로 쉽게 처리할 수 있도록 지원하는 클래스의 집합(패키지)
- 요소들의 Stream에 함수형 연산(람다함수를 통한 연산)을 지원하는 클래스

### 특징

- 데이터 소스로부터 데이터를 읽기만 할 뿐 데이터 소스를 변경하지 않음
- 일회용
- 작업을 내부 반복으로 처리하기 때문에 불필요한 코딩 줄일 수 있음
    
    ```java
    // 기존 for each문
    for(String str : strList) {
    	System.out.println(str)
    }
    // 스트림에 정의된 forEach() 메서드
    stream.forEach(System.out::println);
    ```
    
- `parallel()` 또는 `parallelStream()` 메서드로 병렬처리가 가능
</div>
</ul>
</div>
</details>
