## [17.1.16 月](https://github.com/yseok/day_study/tree/master/summarize/2%EC%A3%BC%EC%B0%A8/170116)
***

# 자바란?
 - [자바](https://ko.wikipedia.org/wiki/%EC%9E%90%EB%B0%94_(%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D_%EC%96%B8%EC%96%B4)) (영어: Java, 문화어: 쟈바)는 썬 마이크로시스템즈의 제임스 고슬링(James Gosling)과 다른 연구원들이 개발한 객체 지향적 프로그래밍 언어.

 > 유닉스 기반의 배경을 가지고 있었기 때문에 문법적인 특성은 파스칼이 아닌 C++의 조상인 C 언어와 비슷하다.[14] 자바를 다른 컴파일언어와 구분짓는 가장 큰 특징은 컴파일된 코드가 플랫폼 독립적이라는 점이다. 자바 컴파일러는 자바 언어로 작성된 프로그램을 바이트코드라는 특수한 바이너리 형태로 변환한다. 바이트코드를 실행하기 위해서는 JVM(자바 가상 머신, Java Virtual Machine)이라는 특수한 가상 머신이 필요한데, 이 가상 머신은 자바 바이트코드를 어느 플랫폼에서나 동일한 형태로 실행시킨다. 때문에 자바로 개발된 프로그램은 CPU나 운영 체제의 종류에 관계없이 JVM을 설치할 수 있는 시스템에서는 어디서나 실행할 수 있다.

# JAVA파일의 Runtime 컴파일
 - JAVA는 VM을 통해 컴파일진행, 각 OS에 맞게 기계어 컴파일

 > JIT (just-in-time compilation) :  동적 번역(dynamic translation)이라고도 하는데, 프로그램을 실제 실행하는 시점에 기계어로 번역하는 컴파일 기법이다. 이 기법은 프로그램의 실행 속도를 빠르게 하기 위해 사용된다. 실행 시점에서 기계어 코드를 생성하면서 그 코드를 캐싱하여, 같은 함수가 여러 번 불릴 때 매번 기계어 코드를 생성하는 것을 방지한다.

 > AOT (ahead-of-time compile) : 목표 시스템의 기계어와 무관하게 중간 언어 형태로 배포된 후 목표 시스템에서 인터프리터나 JIT 컴파일 등 기계어 번역을 통해 실행되는 중간 언어를 미리 목표 시스템에 맞는 기계어로 번역하는 방식. 


# JAVA의 실행과정

![자바실행과정](https://github.com/yseok/day_study/blob/master/image/2%EC%A3%BC%EC%B0%A8/170116/%EC%9E%90%EB%B0%94%EC%8B%A4%ED%96%89%EA%B3%BC%EC%A0%95.png?raw=true)

 > Java Source(.java)를 Byte Code(.class)로 변환하여 JVM을 통하여 실행된다.

# 코드 작성 규칙
 - 식별자

 > 클래스, 함수, 변수의 이름
 > 대소문자 구분.
 > 첫글자에 숫자를 사용할 수 없다.

 - [예약어](https://github.com/yseok/day_study/blob/master/summarize/2%EC%A3%BC%EC%B0%A8/170116/%EC%98%88%EC%95%BD%EC%96%B4.md)
 > 이미 문법적인 용도로 사용되고 있기 때문에 식별자로 사용할 수 없는 단어

 - 기본 자료형

![기본자료형](https://github.com/yseok/day_study/blob/master/image/2%EC%A3%BC%EC%B0%A8/170116/%EA%B8%B0%EB%B3%B8%EC%9E%90%EB%A3%8C%ED%98%95.PNG?raw=true)

 > **기본 자료형**
 >> 논리형 : boolean (1 bit)
 >> 문자형 : char(16 bit), byte(8 bit)
 >> 정수형 : short(16 bit), int(32 bit), long(64 bit)
 >> 실수형 : float(32 bit), double(64 bit)

 >>> String은 많이 쓰지이만 기본 자료형이 아니다.

# 문자형 Data타입의 적용
 - char = '', String = "" 구분 사용

 - 정수형 : byte, short, int, long

 > 데이터를 처리할때는 byte + byte라 하더라도 int로 변환하여 계산
 >> byte + byte = int
 >> short + short = int

 - 실수형 : float, double
 > 소수는 기본적으로 double형으로 인식

 - 소수점 연산 오류 원인

 > 1. 컴퓨터는 HW는 기본적으로 소수점인 0.1을 표현할 수 없다
 > 0과 1의 정수만 표현 가능한데, 소수점 표현을 위해 지수부와 가수부를 구분해서 표시하게 된다
 
 >> 지수가수 표기법

 >> a = 0.1515 *  10E1

 >> b = 0.55 * 10E-5

 >>>풀어쓰기

 >>>a = 1.515
 >>>b = 0.0000055

 >>> 지수가수 표기법으로 변경(가수에 할당된 자리수가 7자리일 경우)
 >>> a + b = 0.15150055 * 10E1 < 1.5150055 
	* 여기서 0.0000005의 오차가 발생한다.
 >>> 가수부가 3자리로 한정되면 아래와 같이 뒷자리가 절삭된다.
 >>> a + b = 0.152 * 10E1
 >>> // 지수 =  10의 몇승 같은표기


# 자바의 제어문
 - 조건문 : 주어진 조건에 대해 분기를 한다
 - 반복문 : 조건에 따라 반복문 블록 안의 로직을 반복적으로 처리한다.
 - 예외처리문 : 예외가 발생했을때 처리한다.

## 조건문 if~ else
 - if : if문은 조건문이다. 즉, 만약 주어진 조건에 true이면 실행되고 false면 실행하지 않는다.
 - else : else는 쓴 숫자가 if의 조건에 맞지 않을때 실행된다. 즉, 조건문의 조건이 false이면 실행되고 true면 실행하지 않는다.

## 조건문 switch ~ case
 - 조건문의 일종인데, 여러 개의 if~else 문을 대신하여 간결하게 작성할 때 사용하는 것.

 > switch문 다음의 괄호()에는 "i <= 0" 이런 식의 판단문이 들어갈 수는 없고, 정수형이나 문자형(char)의 숫자만 들어갈 수 있는 제약이 있다.

## 반복문 for

![for문](https://github.com/yseok/day_study/blob/master/image/2%EC%A3%BC%EC%B0%A8/170116/for%EB%AC%B8.png?raw=true)

 - 형식 : for (변수 초기값; 변수의 값이 ~인 동안 계속; 변수의 변동값)의 형식으로 사용
 - for문 안의 for문을 여러번 중첩하여 사용할 수 있다.


## 반복문 while
 - while 문은 조건이 참일 동안 블럭 안의 로직을 반복 실행
 - do~while문은 로직을 한 번 실행 하고 조건을 실행한다.

## break
 - break는 switch 또는 반복문을 종료

## coutinue
 - continue 시 아래로직은 무시된다.

***

## [17.1.17 火](https://github.com/yseok/day_study/tree/master/summarize/2%EC%A3%BC%EC%B0%A8/170117/pratice)
***

- Pattern Pratice : [1](https://github.com/yseok/day_study/blob/master/summarize/2%EC%A3%BC%EC%B0%A8/170117/pratice/pratice_1_(right_triangle).md), [2](https://github.com/yseok/day_study/blob/master/summarize/2%EC%A3%BC%EC%B0%A8/170117/pratice/pratice_2_(reverse).md), [3](https://github.com/yseok/day_study/blob/master/summarize/2%EC%A3%BC%EC%B0%A8/170117/pratice/pratice_3_(pyramid).md), [4](https://github.com/yseok/day_study/blob/master/summarize/2%EC%A3%BC%EC%B0%A8/170117/pratice/pratice_4_(empty_triangle).md), [5](https://github.com/yseok/day_study/blob/master/summarize/2%EC%A3%BC%EC%B0%A8/170117/pratice/pratice_5_(empty_triangle2).md), [6](https://github.com/yseok/day_study/blob/master/summarize/2%EC%A3%BC%EC%B0%A8/170117/pratice/pratice_6_(diamind).md), [7](https://github.com/yseok/day_study/blob/master/summarize/2%EC%A3%BC%EC%B0%A8/170117/pratice/pratice_7_(empty_diamond).md), [8](https://github.com/yseok/day_study/blob/master/summarize/2%EC%A3%BC%EC%B0%A8/170117/pratice/pratice_8_(X_pattern).md)


***
[17.1.18 水](https://github.com/yseok/day_study/tree/master/summarize/2%EC%A3%BC%EC%B0%A8/170118)
***

#배열
- 배열은 자바에서 하나의 객체이다. 배열을 생성하기 위해서는 반드시 배열을 선언해야 한다.

 > ex) int[] height = new int[11];  or int height[] = new int[11];
 > int[] height와 int height[] 모두 같은것이다.
 > 변수 height는 정수의 배열 (int[])로 선언되었다. height 배열은 height[0] ~ height[10] 까지의 11개의 정수를 저장할 수 있다.
 > 정수형 배열의 각 인덱스는 기본적으로 0 으로 초기화 된다. (String 배열은 null 이다)
 > 여기서 만약 height[11] 과 같이 배열의 범위를 벗어나면 ArrayIndexOutOfBoundsException이 발생한다.
 > Java 배열의 크기는 length 를 사용하여 확인 할 수 있다.
 > height.length  는 11이다. 따라서 height 배열의 마지막 인덱스는 height[height.length-1] 이 된다.


 > - 변수의 집합. 같은 데이터 타입의 변수를 한꺼번에 많이 저장하는 저장소.
 > - 배열의 크기는 첨자로 결정.
 > - 배열의 메모리는 연속으로 잡힘
 > - 배열의 이름은 연속된 변수들을 참조하기 위한 참조 값
 > - 배열도 객체이므로 Heap에 메모리가 할당되며 Object클래스의 메서드 이용가능하다.
 > - 동일한 자료형을 갖는 자료의 배열

- 배열 선언 (선언할 때 크기 명시 안한다.)
 > int[] a or int a[] 


# ArrayList

- 배열처럼 각 자료에 대하여 직접 인덱스를 부여하지 않고 이전 데이터나 다음 데이터에 대한 참조만 가지고 있으므로 데이터를 추가하거나 삭제시 연관된 모든 데이터의 인덱스를 변경할 필요 없이 이전데이터와 다음데이터에 대한 참조만 변경하면 되므로 효율적으로 동작할 수 있다.

 > 단순연결리스트 예시
 >
 > class Node {
 >
 >  private Object data;
 >  private Node nextNode;
 >
 >  Node(Object data){
 >    
 >        this.data = data;
 >        this.nextNode = null;
 >       
 >  }
 >}

- [Array](https://github.com/yseok/day_study/tree/master/summarize/2%EC%A3%BC%EC%B0%A8/170118/Array), [String](https://github.com/yseok/day_study/tree/master/summarize/2%EC%A3%BC%EC%B0%A8/170118/String) Pratice
 > [Bbs_Pratice](https://github.com/yseok/day_study/blob/master/summarize/2%EC%A3%BC%EC%B0%A8/170119/bbs_pratice.md)


***
[17.1.19 木](https://github.com/yseok/day_study/tree/master/summarize/2%EC%A3%BC%EC%B0%A8/170119)

***

#Object란?

프로그래밍에서 객체란 속성과 기능을 가지는 대상을 말한다. 속성과 동작의 개념을 이해하면 객체도 쉽게 이해할 수 있다.

게시판 - 객체
데이터 - 속성

#OPP
- OOP=Object Oriented Programming(객체 지향적 프로그래밍)을 말한다.
- 객체 지향적 프로그래밍에서 사용하는 객체 지향 언어의 특성으로는 캡슐화(Encapsulation),상속(Inheritance),다형성(Polymorphism)이 있다.

#OOP 개발 과정
 - OOP는 기본적으로 구현과 설계를 나누어서 생산성 향상과 관리의 용이성을 추구하는데 그 목적이 있다. OOP 개발과정을 정리하면 아래와 같은데, 그 중에서 설계의 비중이 가장 큰 개발방식이 OOP이다.

##S.O.L.I.D-OOP설계원칙
- SRP ( 단일책임)
> 여러 책임이 섞여있는 클래스를 책임별 분리 
> 코드 변경의 영향이 미치는 범위가 최소화 된다.
>  - Class가 변경되도 다른 Class에 영향을 미치지 않는다.
>  
> 코드 응집성이 향상된다.
>  - 데이터 연관성이 높은 것끼리 인터페이싱이 자주 일어난다. 
>  
>  각 단위 테스트가 용이하다.
>  - 각 Class별 테스트가 가능하다.

- OCP (계방폐쇄)
> 코드 추가만으로 기능 변경이 가능한가

- LSP ( 교체가능)
> 기반 클래스의(Base Class)의 포인터나 참조값을 사용하는 코드에서는 실제로 어떤 클래스인지 몰라도 쓸 수 있어야 한다.(정보 은닉)

- DIP (의존 역전)
> 변경의 주체가 누구인가?

- ISP ( 인터페이스 분리)
> 클라이언트가 클래스의 특정 기능만 이용한다면 기능의 부분 집합을 별도 인터페이스로 추출

***
[17.1.20 金](https://github.com/yseok/day_study/tree/master/summarize/2%EC%A3%BC%EC%B0%A8/170120)
***

#try catch

- JDK 1.7 이상 버전에서의 예외처리
- finally가 없어도 자동으로 close처리해준다

#String 연산
- JDK 1.5 이상의 버전에서의 String연산

- JDK5.0 이상부터는 String의 + 연산을 컴파일러가 자동으로  StringBuilder연산으로 바꿔주지만, 반복문 안에서의 +연산은 여전히 일반 +연산으로 수행하므로 가급적 StringBuilder를 사용한다.


#java NIO package

- New I/O는 JDK1.4에서 새로 추가된 패키지이다. JDK1.4의 정식 명칭은 Java 2 Standard Edition JDK1.4이다.

> - 기본 데이터형용 버퍼를 클래스로 제공해 준다.
> - Character-set 인코더들과 디코더.
> - 패턴과 어울린 기능은 Perl-style 정규식들로 설정.
> - 채널, 새로운 I/O 추상화.
> - 메모리 매핑과 파일의 lock(잡금장치)를 지원해주는 인터페이스.
> - non-blocking 입출력이 가능.

#java IO Stream Package
 - Java에서 데이터는 Stream을 통해 입출력된다. 
 
- 프로그램이 데이터를 입력받을 때에는 InputStream 이라 부르고, 프로그램이 데이터를 보낼 때에는 OutputStream 이라고 부른다.

- Stream은 단방향이므로 프로그램이 다른 프로그램과 데이터를 교환하려면 양쪽 모두 InputStream과 OutputStream이 필요하다.

#java IO Stream Package
 - Java에서 데이터는 Stream을 통해 입출력된다. 
 
- 프로그램이 데이터를 입력받을 때에는 InputStream 이라 부르고, 프로그램이 데이터를 보낼 때에는 OutputStream 이라고 부른다.

 - Stream은 단방향이므로 프로그램이 다른 프로그램과 데이터를 교환하려면 양쪽 모두 InputStream과 OutputStream이 필요하다.


#java IO Stream 구성
 - 스트림은 크게 입력, 출력 두가지 형태로 구분할 수 있는데 바이트 기반 스트림은 이미지, 동영상 ,문자 등 모든 종류의 미디어를 주고받을 수 있는데 반해, 캐릭터 기반 스트림은 문자만 주고 받도록 설계되어 있다.

#IO vs NIO

 - IO와 NIO는 데이터를 입출력한다는 목적은 동이랗지만, 방식에 있어서는 차이점이 있다.

> - 1.스트림 대 채널
채널은 입출력시 하나만 생성하는 반면, 스트림은 입력과 출력 두개 필요

> - 2. non-Buffer vs Buffer
버퍼는 HW/SW 간의 속도차이를 줄여준다. 빠르다. 채널은 기본적으로 버퍼를 사용한다.

3.Blocking vs non-Blocking
스트림은 파일 읽기시 해당 스레드가 블로킹되고 ‌interrupe로 빠져나오는 것도 불가능하다, stream.close()로만 블로킹을 해제할 수 있다.

#NIO Pate처리 (jdk 7 이상)

 - 1. 파이렃리의 간소화를 위해 NIO2 도입 (NIO = new I/O)
 - 2, 경로에 대한 처리를 위해 Path가 추가되었다.
 - 3. 파일의 읽기와 쓰기를 위한 method가 추가되었다.


# NIO File 처리

- 파일과 디렉토리 생성

- 파일 복사, 이동, 삭제


#NIO장점
- 불특정 다수의 클라이언트 연결 또는 멀티 파일들을 넌 블로킹이나 비동기로 처리할 수 있기 때문에 과도한 스레드 생성을 피하고 스레드를 효과적으로 재사용한다는 점에서 큰 장점이 있다.

#IO
- 대용량 데이터를 처리할 경우에는 IO가 더 유리한데, NIO는 버퍼의 할당 크기도 문제가 되고, 모든 입출력 작업에 버퍼를 무조건 사용해야 하므로 받은 즉시 처리하는 IO보다는 좀 더 복잡하다.
