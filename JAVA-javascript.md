# JAVA

[https://data-make.tistory.com/217]

🚩 OOP(Object-Oriented Programming)? 객체 지향 프로그래밍?

- 객체란 하나의 역할을 수행하는 '메소드와 변수(데이터)'의 묶음
- 데이터를 객체로 취급하여 프로그램에 반영, 객체와 객체의 상호작용을 통해 프로그램이 동작
- 각각의 객체는 메시지를 주고받으며 데이터를 처리
- 함수보다 더 높은 모듈 관리를 위해 자신이 가진 고유의 데이터와 그 데이터를 처리할 수 있는 메서드를 가짐
- 모든 데이터를 객체로 취급하므로 객체와 객체 간 자유로운 데이터 이동 가능

🚩 자바의 메모리 영역

- Static Area
  - 필드 부분에서 선언된 변수(전역변수)와 정적 멤버변수(static이 붙은 자료형)를 저
  - Static 영역의 데이터는 프로그램의 시작부터 종료가 될 때까지 메모리에 남음
- Method Area
  - JVM이 실행되면서 생기는 공간
  - Class/전역변수/Static 변수 정보가 저장되는 공간
  - 모든 스레드에서 정보가 공유
- Heap
  - new 연산자로 생성된 객체
  - Heap에 저장된 데이터는 Garbage Collector 가 처리하지 않는한 소멸되지 않는다.
  - `Reference Type 정보`를 저장
  - 모든 스레드에서 정보가 공유
- Stack
  - 지역변수, 메소드의 매개변수와 같이 잠시 사용되고 필요가 없어지는 `데이터가 저장되는 공간`
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

- Primitive type
  - 기본값이 있으므로 Null이 존재하지 않음
  - 실제 값을 `스택 메모리에 저장`
  - boolean, byte, short, int, long, float, double, char ..
- Reference type
  - 기본형 타입을 제외한 타입들이 모두 참조형 타입
  - 빈 객체를 의미하는 Null 존재
  - 값이 저장되어 있는 곳의 주소값을 `힙 메모리`에 저장
  - Array, Enumeration, Class, Interface ..
  

🚩 GC처리 방법

- JVM에서는 Java Application이 사용하는 메모리를 관리하고 있는데 이 JVM의 기능중 더 이상 사용하지 않는 객체를 청소하여 공간을 확보하는 GC 작업이 존재
- GC란 Garbage Collection(쓰레기 객체 정리, 이하 GC)의 약자입니다. Java Runtime시 Heap 영역에 저장되는 객체들을 따로 정리하지 않으면 계속헤서 쌓이게되어 OutOfMemmory Exception이 발생할 수 있습니다. 이를 방지하기 위하여 JVM에서는 주기적으로 사용하지 않는 객체를 수집하여 정리하는 GC를 진행합니다.

1. 객체가 생성되면 Eden 영역에 올라간다.
2. Eden영역이 꽉차면 Servior 영역으로 '살아있는 객체'를 이동시킨다 (객체의 크기가 Servior 영역보다 클 경우  Old 영역으로 이동)
3. Servivor 영역이 꽉 찰경우 Eden, Servivor영역에 남은 객체를 Old 영역으로 이동

[Java의 GC(Garbage Collection)방법과 종류](https://deveric.tistory.com/64)

🚩interface와 abstract의 차이

- `Abstract Method :  자식 클래스에서 반드시 오버라이딩해야만 사용할 수 있는 메소드
  -  추상 메소드가 포함된 클래스를 상속받는 자식 클래스가 반드시 추상 메소드를 구현하도록 하기 위함
- `Interface`는 `공통 기능`이 필요할 때, 각 기능들을 오버라이딩하여 여러가지 형태로 구현할 수 있도록 하는 상속 관계가 아닌 `다형성`과 연관
  - 메소드 형태만 서로 공유해서 구현되
  - 구현 로직이 자주 변경될 경우 주로 사용
  - ex. Vehicle (탈 것은 공통되는 기능이 존재
- `Abstract Class`는 부모와 자식 `상속 관계`에서 Abstract Class를 상속받는 자식 Class들 간에 공통 기능을 각각 구현 및 확장
  - 하나 이상의 추상 메소드를 포함하는 클래스
  - 상속받은 자식 클래스가 반드시 추상클래스의 기능을 사용하도록 하고 확장시키는데 사용
  - ex. Dog (모든 강아지는 비슷하지만 각기 다른 특징이 존재)

🚩String, StringBuilder, StringBuffer 차이

- String
  - immutable(불변), 한번 생성되면 할당된 메모리 공간이 변하지 않음.
  - `+ 연산자` 또는 `concat 메서드`를 통해 String 객체 문자열을 연결할 경우 `새로운 String 객체 생성`
  - 짧은 문자열을 더할 경우 사용
- StringBuffer, StringBuilder
  - mutable
  - 문자열 연산 등으로 기존 객체의 공간이 부족하게 되는 경우, 기존의 버퍼 크기를 늘리며 유연하게 동작
  - StringBuffer는 각 메서드별로 Synchronized Keyword가 존재하여, 멀티스레드 환경에서도 동기화를 지원 `thread safe `
  - StringBuilder는 동기화를 보장하지 않음 `not thread safe `

🚩 접근제어자의 종류와 특성

|   종류    | 클래스 | 동일 클래스 | 하위 패키지 | 모든 클래스 |
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

- static변수와 static메소드를 생성할 경우 정적필드와 정적 메소드라고도 하며, 이 둘을 합쳐 정적 멤버라고 불림 (=클래스 멤버) 
- 클래스 로딩 시 함께 로딩
- GC가 관여하지 않고 모든 객체가 메모리를 공유

🚩 final 키워드

- 상수 표현을 위한 예약어
- final 변수
  - 변수 선언과 동시에 초기화
  - 초기화 이후 값 수정이 불가능하며 접근만 가능
- final 메서드
  - 오버라이딩 불가능
- final 클래스
  - 상속 불가능, subclass 생성 불가능

🚩 오버로딩과 오버라이딩

- 오버로딩(Overloading) : 이름은 동일하지만 입력 항목(인자 개수, 유형)이 다른 메서드
- 오버라이딩(Overriding) : 부모 클래스의 메서드를 자식 클래스가 동일한 형태로 재정의

🚩 쓰레드와 프로세스의 차이

- **프로세스(Process)**
  - 운영체제에서 실행중인 하나의 프로그램(하나 이상의 쓰레드 포함)
-  **쓰레드(Thread)**
  - `하나의 작업 단위`, 한 프로세스 내에 여러 쓰레드가 존재 가능, 해당 쓰레드들은 프로세스의 자원을 공유
  -  쓰레드 생성 방법
    - Thread 클래스 extends 혹은 Runnable 인터페이스 implements (다른 클래스를 상속받은 경우)
    - 익명 클래스 이용하기 (new Thread()), 쓰레드가 단 한번만 수행

- **멀티 쓰레드의 장단점**
  - 두 가지 이상의 작업을 동시에 실행할 수 있어 자원을 효율적으로 이용 가능하지만 dead lock 및 동기화에 대한 철저한 검증 필요
- **동기화(Synchronized)**
  - 멀티 쓰레드 사용 시 공유 자원의 동시 접근을 제어, 자원의 유실 방지

🚩 제네릭, 왜 쓰는지 어디세 써 봤는지 알려주세요.

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

- **Stack**
  - LIFO(Last In First Out) 구조
- **Queue**
  - FIFO (First In First Out) 구조
- **LinkedList**
  - 불연속적(비순차적)으로 존재하는 데이터를 서로 연결(link)한 형태로 구성
  - 데이터 삭제/추가 속도가 빠름

---

🚩 자바 코드의 실행 과정을 설명해주세요.

🚩 JVM, JRE, JDK 를 설명해주세요.





🚩 try-with-resources에 대해 설명하시오.

🚩 Synchronize에 대해 설명하시오.

🚩 Synchronize를 하기 위한 방법은 무엇이 있나요?

🚩 컬렉션 프레임워크에 대해 설명하시오.

🚩 CheckedException과 UnCheckedException의 차이를 설명하시오.

🚩 final / finally / finalize 의 차이를 설명하시오.

🚩 new String()과 ""의 차이에 대해 설명해주세요.

🚩 스프링 IOC가 무엇인가요?

🚩 OOP와 AOP에 대한 차이를 설명해주세요.

🚩 POJO가 무엇인가요?

# JavaScript

shell script 에서의 return
