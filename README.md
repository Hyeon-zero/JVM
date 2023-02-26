# JVM

- JVM(Java Virtual Machine)이란 자바 프로그램 실행 환경을 만들어주는 소프트웨어이다. 
- Java는 OS에 종속적이지 않다는 특징을 가지고 있다. 
- Java는 종속적이지 않기 때문에 CPU가 .java 파일을 인식하지 못한다. 따라서 JVM을 통해 CPU가 java를 인식하여 프로그램을 수행하도록 한다. 
- JVM을 통해 .java → .class(Byte Code) 으로 변환하여 실행 (변환과정을 java compiler(javac.exe)가 실행) 
<br>

## Byte Code를 읽는 방식
  1. Interpreter 방식 : Byte Code를 한 줄씩 읽어 해석하고 실행하는 방식이다. 단점은 속도가 느리다.
  2. JIT(Just In Time) 방식 : Interpreter의 느린 속도를 보완하기 위해 만들어졌다. Byte Code를 실행하는 시점에 각 OS에 맞는 Natvie Code로 변환하여 실행 속도 개선
                         그러나 Byte Code를 Native Code로 변환하는 데에도 비용이 소모되므로 JVM은 모든 코드를 JIT 방식으로 실행하지 않고, Interpreter 방식을
                         사용하다가 일정 기준이 넘어가면 JIT 방식으로 사용한다. 
<br>

## JIT Compiler
   JIT Compiler는 같은 코드를 매번 해석하지 않고, 실행할 때 컴파일을 하면서 해당코드를 캐싱한다. 이후에는 바뀐 부문만 컴파일하고, 나머지는 캐싱된 코드를 사용한다. <br>
<br>


## JVM 동작 방식
  ① Java로 개발된 프로그램을 실행하면 JVM은 OS로부터 Memory를 할당한다. <br>
  ② Java Compiler(javac)가 Java Source Code(.java)를 Java Byte Code(.class)로 compile 한다. <br>
  ③ Class Loader를 통해 JVM Runtime Data Area로 로딩한다. <br>
  ④ Runtime Data Area에 로딩된 .class들은 Execution Engine을 통해 해석한다. <br>
  ⑤ 해석된 Byte Code는 Runtime Data Area의 각 Area에 배치되어 수행하며 이 과정에서 Execution Engine에 의해 <br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;GC(Garbage Collector)의 작동과 Thread Synchronization가 이루어진다. <br>
    
<br>
