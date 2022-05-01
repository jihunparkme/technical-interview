# JAVA

🚩 OOP란? 객체 지향 프로그래밍이란 ?

- Object-Oriented Programming
- 프로그램을 단순히 데이터와 처리 방법으로 나누는 것이 아니라, 프로그램을 수많은 '객체(object)'라는 기본 단위로 나누고 이들의 상호작용으로 서술하는 방식이다. 객체란 하나의 역할을 수행하는 '메소드와 변수(데이터)'의 묶음으로 봐야 한다.

🚩 자바의 메모리 영역에 대해 설명해주세요.

- Method Area
  - JVM이 실행되면서 생기는 공간
  - Class/전역변수/Static 변수 정보가 저장되는 공간
  - 모든 스레드에서 정보가 공유
- Heap
  - new 연산자로 생성된 객체
  - Heap에 저장된 데이터는 Garbage Collector 가 처리하지 않는한 소멸되지 않는다.
  - Reference Type 의 데이터가 저장되는 공간
  - 모든 스레드에서 정보가 공유
- Stack
  - 지역변수, 메소드의 매개변수와 같이 잠시 사용되고 필요가 없어지는 데이터가 저장되는 공간
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

🚩 GC처리 방법에 대해 설명하시오.

🚩

🚩

🚩





Interface와 Abstract에 대해 말해주세요.

스트링과 스트링버퍼의 차이에 대해 설명해주세요.

접근제어자의 종류와 특성에 대해 설명해보세요.

쓰레드를 구현하기 위한 인터페이스, 클래스는 무엇이 있나요?

static 키워드에 대해 설명해주세요.

자바 코드의 실행 과정을 설명해주세요.

오버로딩과 오버라이딩에 대해 설명해주세요.

쓰레드와 프로세스의 차이는 무엇일까요?

JVM, JRE, JDK 를 설명해주세요.

final 키워드에 대해 설명해주세요.

스택과 링크드리스트와 리스트의 차이점을 설명해 보세요.

JVM구조에 대해 설명하시오.



HashMap vs HashTable vs ConcurrentHashMap의 차이를 설명하시오.

접근제어자에 대해 설명하시오.

interface와 abstract의 차이를 설명하시오.

StringBuilder와 StringBuffer의 차이에 대해 설명하시오.

try-with-resources에 대해 설명하시오.

Synchronize에 대해 설명하시오.

Synchronize를 하기 위한 방법은 무엇이 있나요?

static은 메모리 구조 중 어디에 올라가나요?

컬렉션 프레임워크에 대해 설명하시오.

제네릭에 대해 설명해주시고, 왜 쓰는지 어디세 써 봤는지 알려주세요.

Vector와 List 차이에 대해 설명하시오.

오버로딩과 오버라이딩의 차이는?

CheckedException과 UnCheckedException의 차이를 설명하시오.

final / finally / finalize 의 차이를 설명하시오.

new String()과 ""의 차이에 대해 설명해주세요.

스프링 IOC가 무엇인가요?

OOP와 AOP에 대한 차이를 설명해주세요.

POJO가 무엇인가요?



# JavaScript

shell script 에서의 return