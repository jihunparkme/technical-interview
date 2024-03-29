# JAVA

[https://data-make.tistory.com/217]

🚩 OOP(Object-Oriented Programming)와 객체 지향 프로그래밍

- `객체`란 하나의 역할을 수행하는 `'메소드와 변수(데이터)'의 묶음`
- 실제 데이터를 객체로 취급하여 프로그램에 반영
- 객체와 객체는 메시지를 주고받으며 데이터를 처리하는 상호작용을 통해 프로그램이 동작
- 함수보다 더 높은 모듈 관리를 위해 자신이 가진 고유의 데이터와 그 데이터를 처리할 수 있는 메서드를 가짐

🚩 자바의 메모리 영역

- Static Area
  - 필드 부분에서 선언된 변수(`전역변`수)와 정적 `멤버변수`(static이 붙은 자료형)를 저장
  - Static 영역의 데이터는 프로그램의 시작부터 종료가 될 때까지 메모리에 남음
- Method Area
  - JVM이 실행되면서 생기는 공간
  - Class/전역변수/Static 변수 정보가 저장되는 공간
  - 모든 스레드에서 정보가 공유
- Heap
  - `new 연산자로 생성된 객체`
  - Heap에 저장된 데이터는 Garbage Collector 가 처리하지 않는한 소멸되지 않는다.
  - `Reference Type 정보`를 저장
  - 모든 스레드에서 정보가 공유
- Stack
  - 지역변수, 메소드의 매개변수와 같이 `잠시 사용되고 필요가 없어지는 데이터`가 저장되는 공간
  - Last In First Out
  - 지역변수 이지만 Reference Type일 경우에는 Heap 에 저장된 데이터의 주소값을 Stack 에 저장해서 사용
  - 스레드마다 하나씩 존재
- PC Register
  - 스레드가 생성되면서 생기는 공간
  - 스레드가 어느 명령어를 처리하고 있는지 그 주소를 등록
  - JVM이 실행하고 있는 현재 위치를 저장
- Native Method Stack
  - Java 가 아닌 다른 언어 (C, C++) 로 구성된 메소드를 실행이 필요할 때 사용되는 공간

[자바의 메모리 구조](https://velog.io/@shin_stealer/%EC%9E%90%EB%B0%94%EC%9D%98-%EB%A9%94%EB%AA%A8%EB%A6%AC-%EA%B5%AC%EC%A1%B0)

🚩 Primitive type vs Reference type

- `Primitive type`
  - 기본값이 있으므로 Null이 존재하지 않음
  - 실제 값을 `스택 메모리에 저장`
  - boolean, byte, short, int, long, float, double, char ..
- `Reference type`
  - 기본형 타입을 제외한 타입들이 모두 참조형 타입
  - 빈 객체를 의미하는 Null 존재
  - 값이 저장되어 있는 곳의 주소값을 `힙 메모리`에 저장
  - Array, Enumeration, Class, Interface ..
  

🚩 GC처리 방법

- JVM에서는 Java Application이 사용하는 메모리를 관리하고 있는데 이 JVM의 기능중 `더 이상 사용하지 않는 객체를 청소하여 공간을 확보`하는 GC 작업이 존재
- GC란 Garbage Collection(쓰레기 객체 정리, 이하 GC)의 약자입니다. Java Runtime시 Heap 영역에 저장되는 객체들을 따로 정리하지 않으면 계속헤서 쌓이게되어 `OutOfMemmory Exception이 발생`할 수 있습니다. 이를 방지하기 위하여 `JVM에서는 주기적으로 사용하지 않는 객체를 수집하여 정리하는 GC를 진행`합니다.

1. 객체가 생성되면 Eden 영역에 올라간다.
2. Eden영역이 꽉차면 Servior 영역으로 '살아있는 객체'를 이동시킨다 (객체의 크기가 Servior 영역보다 클 경우  Old 영역으로 이동)
3. Servivor 영역이 꽉 찰경우 Eden, Servivor영역에 남은 객체를 Old 영역으로 이동

[Java의 GC(Garbage Collection)방법과 종류](https://deveric.tistory.com/64)

🚩interface와 abstract의 차이

**Abstract Class**

- 부모와 자식 `상속 관계`에서 Abstract Class를 상속받는 자식 Class들 간에 공통 기능을 각각 구현 및 확장
- `하나 이상의 추상 메소드를 포함`하는 클래스
- `상속받은 자식 클래스가 반드시 추상클래스의 기능을 사용`하도록 하고 확장시키는데 사용
- ex. Dog (모든 강아지는 비슷하지만 각기 다른 특징이 존재)

**Abstract Method**

- 자식 클래스에서 반드시 오버라이딩해야만 사용할 수 있는 메소드
- 추상 메소드가 포함된 클래스를 `상속받는 자식 클래스가 반드시 추상 메소드를 구현`하도록 하기 위함

**Interface**

- `공통 기능`이 필요할 때, 각 기능들을 오버라이딩하여 여러가지 형태로 구현할 수 있도록 하는 상속 관계가 아닌 `다형성`과 연관
- 메서드 형태만 서로 공유해서 구현
- 구현 로직이 자주 변경될 경우 주로 사용
- ex. Vehicle (탈 것은 공통되는 기능이 존재)

🚩String, StringBuilder, StringBuffer 차이

**String**

- `immutable`(불변), 한번 생성되면 할당된 메모리 공간이 변하지 않음.
- `+ 연산자` 또는 `concat 메서드`를 통해 String 객체 문자열을 연결할 경우 `새로운 String 객체 생성`
- 주로 짧은 문자열을 더할 경우 사용

**StringBuffer, StringBuilder**

- `mutable`
- 문자열 연산 등으로 기존 객체의 공간이 부족하게 되는 경우, 기존의 버퍼 크기를 늘리며 유연하게 동작
- StringBuffer는 각 메서드별로 Synchronized Keyword가 존재하여, 멀티스레드 환경에서도 동기화를 지원 `thread safe `
- StringBuilder는 동기화를 보장하지 않음 `not thread safe `

🚩 접근제어자의 종류와 특성

|   종류    | 클래스 내부 | 패키지 | 상속 클래스 | 이외 영역 |
| :-------: | :----: | :---------: | :---------: | :---------: |
|  private  |   O    |      X      |      X      |      X      |
| (default) |   O    |      O      |      X      |      X      |
| protected |   O    |      O      |      O      |      X      |
|  public   |   O    |      O      |      O      |      O      |

🚩 Thread Class와 Runnable Interface

|                    Thread Class                    |                Runnable Interface                |
| :------------------------------------------------: | :----------------------------------------------: |
|       고유 한 객체를 만들어 해당 객체와 연관       |            실행 가능 인스턴스를 공유             |
|               더 많은 메모리를 필요                | 같은 오브젝트 공간을 공유하므로 적은 메모리 필요 |
|              다른 클래스 상속 불가능               |             다른 클래스를 상속 가능              |
| 다른 메소드를 오버라이드하거나 특수화해야하는 경우 |           Run 메소드 만 특수화할 경우            |

🚩 static 키워드

- static변수와 static메소드를 생성할 경우 `정적필드`와 `정적 메소드`라고도 하며, 이 둘을 합쳐 `정적 멤버`라고 불림 (=클래스 멤버) 
- 클래스 로딩 시 함께 로딩
- GC가 관여하지 않고 모든 객체가 메모리를 공유

🚩 final 키워드

- `상수 표현`을 위한 예약어

**final 변수**

- 변수 선언과 동시에 초기화
- 초기화 이후 값 수정이 불가능하며 접근만 가능

**final 메서드**

- 오버라이딩 불가능

**final 클래스**

- 상속 불가능, subclass 생성 불가능

🚩 오버로딩과 오버라이딩

**오버로딩(Overloading)**

- 이름은 동일하지만 입력 항목(인자 개수, 유형)이 다른 메서드

**오버라이딩(Overriding)**

- 부모 클래스의 메서드를 자식 클래스가 동일한 형태로 재정의

🚩 쓰레드와 프로세스의 차이

**프로세스(Process)**

- 운영체제에서 실행중인 하나의 프로그램(하나 이상의 쓰레드 포함)

**쓰레드(Thread)**

- `하나의 작업 단위`, 한 프로세스 내에 여러 쓰레드가 존재 가능, 해당 쓰레드들은 프로세스의 자원을 공유
-  쓰레드 생성 방법
  - Thread 클래스 extends 혹은 Runnable 인터페이스 implements (다른 클래스를 상속받은 경우)
  - 익명 클래스 이용하기 (new Thread()), 쓰레드가 단 한번만 수행

**멀티 쓰레드의 장단점**

- 두 가지 이상의 작업을 동시에 실행할 수 있어 자원을 효율적으로 이용 가능하지만 dead lock 및 동기화에 대한 철저한 검증 필요

**동기화(Synchronized)**

- 멀티 쓰레드 사용 시 공유 자원의 동시 접근을 제어, 자원의 유실 방지

🚩 제네릭, 왜 쓰는지, 어디서 써보았는지 

-  클래스 내부에서 사용할 데이터 타입을 외부에서 지정하는 기법 `<T>`
- 클래스나 메소드에서 사용할 내부 데이터 타입을 컴파일 시에 미리 지정
- 클래스나 메소드 내부에서 사용되는 객체의 타입 안정성을 높이고, 반환값에 대한 타입 변환 및 타입 검사에 들어가는 노력을 줄일 수 있음
- 기존 Object 타입의 경우 타입 변환과 오류 발생 가능성이 존재

```java
class MyArray<T> {
    T element;
    void setElement(T element) { this.element = element; }
    T getElement() { return element; }
}

MyArray<Integer> myArr = new MyArray<Integer>();
```

[제네릭의 개념](http://www.tcpschool.com/java/java_generic_concept)

🚩 HashMap vs HashTable vs ConcurrentHashMap 차이

|                          |   HashMap   |                   HashTable                    |                   ConcurrentHashMap                    |
| ------------------------ | :---------: | :--------------------------------------------: | :----------------------------------------------------: |
| key-value에 null 허용    |      O      |                       X                        |                           X                            |
| 동기화 보장(Thread-safe) |      X      |                       O                        |                           O                            |
| 추천 환경                | 싱글 쓰레드 |                  멀티 쓰레드                   |                      멀티 쓰레드                       |
| Lock                     |      X      | 쓰레드간 락을 걸어 데이터를 다루는 속도가 느림 | Entry 아이템별로 락을 걸어 데이터를 다루는 속도가 빠름 |

[HashMap vs HashTable vs ConcurrentHashMap](https://tecoble.techcourse.co.kr/post/2021-11-26-hashmap-hashtable-concurrenthashmap/)

🚩 Stack, Queue, LinkedList

**Stack**

- LIFO(Last In First Out) 구조

**Queue**

- FIFO (First In First Out) 구조

**LinkedList**

- 불연속적(비순차적)으로 존재하는 데이터를 서로 연결(link)한 형태로 구성
- 데이터 삭제/추가 속도가 빠름

🚩 new String()과 ""의 차이

**new String()**

- 새로운 객체를 만드는 것으로 `heap area`에 저장

**String str = "";** 

- 리터럴을 이용한 변수 할당은, `string constant pool`영역에 저장되기 때문에 서로 잠조하고 있는 레퍼런스 주소가 다르다.

🚩 CheckedException과 UnCheckedException의 차이

**CheckedException**

- RuntimeException을 상속하지 않는 클래스

**UnCheckedException**

- RuntimeException을 상속한 클래스

|           구분               |   Checked Exception   |                  Unchecked Exception                    |
| ------------------------ | :---------: | :--------------------------------------------: |
| 확인 시점    |      컴파일 시점      |                       런타임 시점                        |
| 처리 여부 |      반드시 예외 처리      |                       명시적으로 하지 않아도 됨                        |
| 트랜잭션 처리                | 예외 발생시 롤백을 하지 않음 |                  예외 발생시 롤백을 해야 함                   |
| 종류 | IOExceoption, ClassNotFoundException.. | NullPointException, ClassCastException... |
🚩 자바 코드의 실행 과정

- `.java` -> 컴파일러 -> `.class` -> (로딩 -> 배치 -> `실행`) JVM
- .java 파일을 Java 컴파일러가 가상 기계어 파일인 .class 파일(Java Byte Code)로 생성
- 이후 Java Byte Code를 JVM이 읽고 실행

🚩 JVM, JRE, JDK 

**JVM**

-  자바 가상머신(Java Virtual Machine)
- 자바 소스코드로부터 만들어지는 자바 바이너리 파일(.class)을 실행
- 컴파일된 바이너리 코드는 어떤 JVM에서도 동작

**JRE**

- 자바 실행환경(Java Runtime Environment)
- JVM 이 자바 프로그램을 동작시킬 때 필요한 라이브러리 파일들과 기타 파일들을 가지고 있음
- JVM의 실행환경을 구현

**JDK**

-  자바 개발도구(Java Development Kit)
- JRE + 개발을 위해 필요한 도구(javac, java등)들을 포함

🚩 try-with-resources

- 선언된 객체들에 대해서 `try가 종료될 때 자동으로 자원을 해제`해주는 기능
- try에서 선언된 객체가 `AutoCloseable`을 구현하였다면 Java는 try구문이 종료될 때 객체의 `close()` 메소드를 호출

🚩 Synchronize

- 멀티 쓰레드 환경에서 두개 이상의 쓰레드가 하나의 변수에 동시에 접근을 할 때 Race condition(경쟁상태)이 발생하지 않도록 하기 위해 사용

🚩 Synchronize를 하기 위한 방법

- synchronized block을 사용

```java
synchronized (SynchronizedKeywordExample.class) {
    number++;
    System.out.println(number);
}
```

🚩 컬렉션 프레임워크

- `데이터를 저장하는 자료 구조`와 `데이터를 처리하는 알고리즘`을 구조화하여 클래스로 구현해 놓은 것
- List / Set / Map 인터페이스
- [컬렉션 프레임워크의 개념](http://www.tcpschool.com/java/java_collectionFramework_concept)

🚩 final / finally / finalize 의 차이를 설명하시오.

**final**

- final 변수 : `상수` 선언
- final 메서드 : 다른 클래스가 이 클래스를 상속할 때 `메소드 오버라이딩 금지`
- final 함수 : 다른 클래스에서 이 클래스를 `상속 금지`

**finally**

- `try-catch`와 함께 사용
- `try-catch`가 종료될 때 finally block이 항상 수행

**finalize**

- Object 클래스에 선언된 protected 메소드
- Garbage collector가 어떤 객체를 참조하는 객체가 없다고 생각되면, 이 객체를 소멸(`finalize()` 메소드를 호출)


🚩 Spring DI
- DI(Dependency Injection)란 **의존 관계 주입** 기능
- **객체를 직접 생성하는 게 아니라 외부에서 생성한 후 주입** 시켜주는 방식
  - `@Autowired`, `@requiredargsconstructor`
- DI(의존성 주입)를 통해서 모듈 간의 결합도가 낮아지고 유연성이 높아진다.

🚩 Spring IOC
- IoC(Inversion of Control)란 제어의 역전
- **프로그램의 제어 흐름**(메소드나 객체의 호출작업)을 직접 제어하는 것이 아니라 외부에서 관리하는 것
- 스프링 애플리케이션에서는 **오브젝트(빈)의 생성과 의존 관계 설정, 사용, 제거 등의 작업을 애플리케이션 코드 대신 스프링 컨테이너가 담당**
- 스프링 애플리케이션의 객체(빈)을 IoC 컨테이터가 관리해줌으로써 개발자의 부담이 줄고 비즈니스 로직에 더욱 집중할 수 있다는 장점
- 객체 간의 결합도를 줄이고 유연한 코드를 작성할 수 있게 하여 가독성 및 코드 중복, 유지 보수를 편하게 할 수 있게 한다.

🚩 OOP와 AOP에 대한 차이를 설명해주세요.

**OOP**(Object Oriented Programming, 객체지향 프로그래밍)

- 모든 데이터를 현실에 빗대어 객체로 다루는 프로그래밍 기법
- 객체지향 언어의 5가지 특징
  - 캡슐화 (Encapsulation) : 데이터와 함수를 하나로 묶는다.
  - 정보은닉 (Information Hiding) : private으로 선언한 데이터는 자기 자신을 통해서만(setter, getter) 접근 가능하다.
  - 추상화 (Abstraction) : 불필요한 부분은 생략하고 중요한 것에만 초점을 맞춰 모델로 만든다.
  - 상속성 (Inheritance) : 부모클래스에 정의된 모든 것을 자식 클래스가 물려받는다.
  - 다형성 (Polymorphism) : 호출하는 객체에 따라 다른 동작을 한다.

**AOP**(Aspect Oriented Programming) - 관점 지향 프로그래밍

- OOP를 더욱 발전시키기 위한 개념
- 하나의 소프트웨어가 하나의 거대한 OOP로써 설계, 프로그래밍 되었다면 이것을 각 기능별로 모듈화해서 분리를 시키는 개념

🚩 POJO가 무엇인가요?
- Plain Old Java Object, 단순한 자바 오브젝트
- 객체 지향적인 원리에 충실하면서 환경과 기술에 종속되지 않고 필요에 따라 재활용될 수 있는 방식으로 설계된 오브젝트
- POJO에 애플리케이션의 핵심로직과 기능을 담아 설계하고 개발하는 방법을 POJO 프로그래밍



Functional Interface

Java CompletableFuture

OOP(Object-Oriented Programming)의 주요 원칙 네 가지에 대해 설명해주세요.

Java에서 ==와 equals() 메서드의 차이점은 무엇인가요?

String, StringBuilder, StringBuffer의 차이점은 무엇인가요?

Java의 예외 처리 방법에 대해 설명해주세요. Checked Exception과 Unchecked Exception의 차이점은 무엇인가요?

JVM의 구조에 대해 설명해주세요. Garbage Collection의 작동 원리에 대해서도 설명해주세요.

JIT 컴파일러란 무엇이며, 어떤 역할을 하나요?

메모리 누수(memory leak)란 무엇이며, Java에서 메모리 누수를 방지하기 위한 방법은 무엇인가요?

Java에서 스레드를 생성하는 방법에는 어떤 것들이 있나요? Runnable과 Thread 클래스의 차이점은 무엇인가요?

동기화(Synchronization)의 개념과 필요성에 대해 설명해주세요. synchronized 키워드의 작동 원리는 무엇인가요?

Deadlock이란 무엇이며, 어떻게 예방할 수 있나요?

Lambda 표현식이란 무엇이며, 어떻게 사용하나요?

Stream API의 주요 특징과 사용 사례를 설명해주세요.

Java에서 제공하는 동기화 방법은? Java Collection / Stream의 차이는?

Optional 클래스의 목적과 사용 방법에 대해 설명해주세요.

싱글톤(Singleton) 패턴이란 무엇이며, Java에서 어떻게 구현하나요?

팩토리 메서드(Factory Method) 패턴과 추상 팩토리(Abstract Factory) 패턴의 차이점은 무엇인가요?

MVC(Model-View-Controller) 아키텍처 패턴에 대해 설명해주세요.

Collection 프레임워크 내의 List, Set, Map의 차이점과 사용 사례를 설명해주세요.

데드락(Deadlock)을 경험한 적이 있나요? 만약 있다면, 그 상황을 어떻게 해결했나요?

최근에 작업한 프로젝트에서 가장 기술적으로 도전적이었던 문제는 무엇이었고, 어떻게 해결했나요?

Override / Overloading 차이점?

ArrayList의 Add 메소드가 내부적으로 어떻게 작동하는지, String의 subString 메소드가 내부적으로 어떻게 작동하는지.

CopyOnArray, CopyOnWrite 자료구조의 의미를 설명해달라.