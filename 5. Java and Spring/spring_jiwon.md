# 5주차 : 스프링 (이지원)

### 🎨 공통 질문
<details>
<summary><strong>IoC(Inversion of Control, 제어의 역전)이 무엇인지 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### IoC(Inversion of Control, 제어의 역전)

- 객체의 생성, 생명주기의 관리까지 모든 객체에 대한 제어권이 바뀌었다는 것
- 소프트웨어 개발에서 모듈 간의 결합도를 줄이기 위해 제어의 반전을 권장하는 디자인 원칙
- 모든 객체에 대한 (생성, 생명주기 등) 제어권을 개발자가 아닌 **IoC 컨테이너**에 넘긴 것
⇒ 객체관리 주체가 프레임워크(컨테이너)가 되기 때문에 개발자는 로직에 집중할 수 있는 장점

### IoC 컨테이너

> 컨테이너 : 객체의 생명주기를 관리하며, 생성된 인스턴스들에게 추가적인 기능을 제공하도록 하는 것
> 
- 스프링 프레임워크에 있는 객체를 생성하고 관리하고 책임지고 의존성을 관리해주는 컨테이너 (= 스프링 컨테이너)
- IoC 컨테이너가 관리하는 객체 : **빈(Bean)**
</div>
</ul>
</div>
</details>
<details>
<summary><strong>DI(Dependency Injection, 의존관계 주입)가 무엇인지 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### DI(Dependency Injection, 의존관계 주입)

- IoC 원칙을 구현하는 디자인 패턴 중 하나
- 필요한 객체를 직접 생성하는 것이 아닌 외부로부터 객체를 받아서 사용하는 것
⇒ 객체 간의 결합도 줄이고 코드 재사용성 높일 수 있음

> **의존관계**
> 
> 
> ex. A가 B에 의존하고 있다
> 
> = B가 변화하면 A에 영향을 줄 수 있다
> 
> B의 기능이 추가 혹은 변경되거나 형식이 바뀌면 그 영향이 A로 전달되는 것
> 
> 방향성이 있기 때문에 B는 A의 변화에 영향을 받지 않음
> 
> A에서 B에 정의된 메소드 호출하는 경우 → 의존관계 있음
> 

### 의존성 주입 방법

1. 생성자 주입
    
    ```java
    @Controller
    public class StudyController {
    		//final을 붙일 수 있음
    		private final StudyService studyService;
    		//---------------------------------------------------------
    		//@Autowired
    		public StudyController(StudyService studyService) {
    				this.studyService = studyService;
    		}
    }
    ```
    
    - 생성자를 통해 의존 관계 주입하는 방법
    - 클래스의 생성자가 하나이고, 그 생성자로 주입받을 객체가 빈으로 등록되어 있다면 `@Autowired` 생략 가능
2. 필드 주입
    
    ```java
    @Controller
    public class StudyController {
    		@Autowired
    		private StudyService studyService;
    }
    ```
    
    - 필드에 바로 의존 관계 주입하는 방법
    - 필드에 `@Autowired` 어노테이션만 붙여주면 자동으로 의존성 주입
    - 코드가 간결하지만, 외부에서 변경하기 힘듦
    - 프레임워크에 의존적이고 객체지향적으로 좋지 않음
3. 수정자 주입
    
    ```java
    @Controller
    public class StudyController {
    		private StudyService studyService;
    		
    		@Autowired
    		public void setStudyService(StudyService studyService) {
    				this.studyService = studyService;
    		}
    }
    ```
    
    - 필드 값을 변경하는 Setter를 통해서 의존 관계를 주입하는 방법
    - Setter 메소드에 `@Autowired` 어노테이션을 붙이는 방법
    - 수정자 주입을 사용하면 setXXX 메서드를 public으로 열어두어야 하기 때문에 언제 어디서든 변경 가능

### **생성자 주입을 권장하는 이유**

1. 순환 참조 방지 가능
    
    A가 B를 참조하고, B가 다시 A를 참조하는 순환 참조되는 코드
    
    ```java
    @Service
    public class AService {
    		// 순환 참조
    		@Autowired
    		private BService bService;
    		
    		public void HelloA() {
    				bService.HelloB();
    		}
    }
    ```
    
    ```java
    @Service
    public class BService {
    		// 순환 참조
    		@Autowired
    		private AService aService;
    		
    		public void HelloB() {
    				aService.HelloA();
    		}
    }
    ```
    
    ⇒ 필드 주입과 수정자 주입은 빈이 생성된 후에 참조를 하기 때문에 어플리케이션이 아무런 오류와 경고 없이 구동됨 → 실제 코드가 호출될 때까지 문제를 알 수 없다는 것
    
    ↔ 생성자를 통해 주입하고 실행하면 `BeanCurrentlyInCreationException` 발생
    
    어플리케이션을 실행하는 시점에서 오류 체크 가능
    
2. 불변성
    
    생성자로 의존성 주입할 때 final로 선언할 수 있고, 이로 인해 런타임에서 의존성을 주입받는 객체가 변할 일 없음
    
    ↔ 수정자 주입은 불필요하게 수정의 가능성을 열어두게 됨, 필드 주입 방식은 null이 만들어질 가능성이 있는데, final로 선언한 생성자 주입 방식은 null 불가능
    
3. 테스트 용이
</div>
</ul>
</div>
</details>
<details>
<summary><strong>Bean 객체와 Bean 생명주기에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### Bean

- DI 컨테이너 내부에 존재하며 관리를 받고 있는 객체
    
    > 자바 어플리케이션은 어플리케이션 동작을 제공하는 객체들로 이루어져 있음
    > 
    > 
    > 이때 객체들은 독립적으로 동작하는 것보다 서로 상호작용하여 동작하는 경우가 많음
    > 
    > 이렇게 상호작용하는 객체 ← **객체의 의존성**
    > 
- 스프링 컨테이너에 의해 관리되는 재사용 가능한 소프트웨어 컴포넌트
- 스프링 컨테이너에 등록한 객체

### Bean 등록하는 방법

1. 컴포넌트 스캔과 자동 의존관계 설정
    - 클래스 선언부 위에 `@Component` 어노테이션 사용하는 것
    - `@Controller`, `@Service`, `@Repository` 모두 `@Component`를 포함하고 있으며 해당 어노테이션으로 등록된 클래스들은 스프링 컨테이너에 의해 자동으로 생성되어 스프링 빈으로 등록
2. 자바 코드로 직접 스프링 빈 등록
    - 설정 클래스를 만들고 `@Configuration` 어노테이션을 클래스 선언부 위에 추가
    - 해당 클래스 안에서 빈으로 등록할 메소드를 만들고 `@Bean` 어노테이션을 붙여주면 자동으로 해당 타입의 빈 객체 생성

### Bean 생명주기

> 스프링 컨테이너 생성 → 스프링 빈 생성 → 의존관계 주입 → 초기화 콜백 메소드 호출 → 사용 → 소멸 전 콜백 메소드 호출 → 스프링 종료
> 
- 스프링 컨테이너에 의해 생명주기 관리
- 스프링 컨테이너 초기화 시 빈 객체 생성, 의존 객체 주입 및 초기화
- 생성과 의존관계 주입과 초기화 분리
    - 생성자는 파라미터를 받고 메모리를 할당해서 객체를 생성하는 책임을 가짐
    - 초기화는 이렇게 생성된 값들을 활용해서 외부 커넥션을 연결하는 등 무거운 동작 수행
    - 따라서 생성자 안에서 무거운 초기화 작업을 함께 하는 것보다 객체를 생성하는 부분과 초기화 하는 부분을 명확하게 나누는 것이 **유지보수 관점**에서 좋음
</div>
</ul>
</div>
</details>
<details>
<summary><strong>AOP에 대해 설명해주세요.</strong></summary>
<div markdown="1">
<ul>
<div>

### AOP(Aspect Oriented Programming)

- 관점 지향 프로그래밍
- 기능을 핵심 관심 사항과 공통 관심 사항으로 분리하여 각각을 모듈화하는 것
- 각 소스코드에서 여러 번 반복해서 사용하는 코드를 흩어진 관심사라고 부르고, 이것을 Aspect로 모듈화해 핵심 로직에서 분리해 재사용하는 것

```java
Class A {
		method a() {
		AAAA
		business Logic..
		BBBB
		}
		
		method b() {
		AAAA
		business Logic..
		BBBB
		}
}

Class B {
		method c() {
		AAAA
		business Logic..
		BBBB
		}
}
```

> 핵심 기능을 하는 business Logic과 부가기능을 하는 코드 AAAA, BBBB
> 
> 
> AAAA, BBBB가 여기저기서 사용되고 흩어져 있기 때문에 코드 변경이 필요한 경우 일일이 다 찾아서 바꿔줘야 함
> 
> ⇒ “AOP는 여러 곳에서 사용되는 중복된 코드를 떼어내서 분리하고, method a,b,c는 각각 business Logic만을 가지고 있자” 라는 개념
> 
> 여기서 AAAA, BBBB가 AOP에서 말하는 Aspect
> 

### AOP 장점

- 중복 코드 제거
- 재활용성 극대화
- 변화 수용 용이성
</div>
</ul>
</div>
</details>
