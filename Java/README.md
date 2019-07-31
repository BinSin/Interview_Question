# Java
- [Java의 특징](#java의-특징)
- [Java EE vs Java SE](#java-ee-vs-java-se)
- [객체 지향 프로그래밍](#객체-지향-프로그래밍)
  - [OOP의 특징](#oop의-특징)
  - [Object](#object)
  - [Overloading vs Overriding](#overloading-vs-overriding)
- [Collection](#collection)
  - [Set](#set)
    - [HashSet](#hashset)
    - [TreeSet](#treeset)
  - [List](#list)
    - [Vector](#vector)
    - [ArrayList](#arraylist)
    - [LinkedList](#linkedlist)
- [Map](#map)
  - [Hashtable](#hashtable)
  - [HashMap](#hashmap)
  - [TreeMap](#treemap)
- [Java의 메모리 영역](#java의-메모리-영역)
- [접근 제어자](#접근-제어자)
- [Abstract와 Interface](#abstract와-interface)
  - [Interface](#interface)
  - [Abstract](#abstract)
  - [Interface 사용 이유](#interface-사용-이유)
- [Serialization](#serialization)
- [Process vs Thread](#process-vs-thread)
  - [Thread를 구현하는 방법](#thread를-구현하는-방법)
- [Static](#static)
  - [Static 단점](#static-단점)
- [Call by Reference vs Call by Value](#call-by-reference-vs-call-by-value)
- [Primitive type vs Reference type](#primitive-type-vs-reference-type)
- [Generic](#generic)
- [Wrapper Class](#wrapper-class)
  - [사용 이유](#사용-이유)
  - [Boxing vs Unboxing](#boxing-vs-unboxing)
- [String vs StringBuffer vs StringBuilder](#string-vs-stringbuffer-vs-stringbuilder)
- [Java8 버전 추가 기능](#java8-버전-추가-기능)
  - [Lambda Function](#lambda-function)
    - [장단점](#장단점)
    - [기본 문법](#기본-문법)
    - [문법 요약](#문법-요약)
  - [Stream](#stream)
    - [장점](#장점)
    - [사용법](#사용법)
      - [중개 연산](#중개-연산)
      - [최종 연산](#최종-연산)
      - [주의점](#주의점)
- [Exception](#exception)
  - [Error vs Exception](#error-vs-exception)
  - [Runtime Exception](#runtime-exception)

## Java의 특징
1. 자바는 네트워크 상에서 쓸 수 있도록 개발한 **객체 지향 프로그래밍 언어**이다.
2. **Java Virtual Machine**만 설치하면 컴퓨터의 OS에 상관없이 작동한다. (즉, **운영체제에 독립적**이다.)
3. 기본 자료형을 제외한 모든 요소들이 **객체로 표현 가능**하다.
4. 객체 지향 개념의 특징인 **캡슐화, 상속성, 다형성**이 잘 적용된 언어이다.
5. **Garbage Collector를 통한 자동적인 메모리 관리**가 가능하다.
6. **멀티쓰레드**를 지원한다.

## Java EE vs Java SE
- Java EE : Java Platform EnterPrise Edition의 약자로 자바를 이용한 **서버측 개발**을 위한 플랫폼
- Java SE : Java Platform Standard Edition의 약자로 데스크톱, 서버, 임베디드를 위한 표준 자바 플랫폼, 주로 **안드로이드 개발**시에 사용한다.

## 객체 지향 프로그래밍
- **실제 세계의 데이터를 객체로 취급**하여 그 객체와의 상호작용을 통해 프로그램이 동작하는 것을 말한다.

### OOP의 특징
1. **코드의 재사용성**이 높다.
2. **코드의 관리가 용이**하여 쉽게 코드를 변경할 수 있다.
3. 제어자와 메서드를 이용하여 데이터를 보호하고, 코드의 중복을 제거함으로써 **신뢰성이 높은 프로그래밍**을 가능하게 한다.

### Object
- 객체는 객체 지향 프로그래밍에서 데이터와 그 데이터에 관련되는 동작을 모두 포함한 개념이다.

### Overloading vs Overriding
- Overloading
  - 클래스 내에 **같은 이름의 메소드를 여러 개 정의하는 것**이다.
  - 매개변수의 타입이 다르거나 개수가 달라야 한다.

- Overriding
  - **부모 클래스의 메소드를 하위 클래스에서 상속받아 재정의하는 것**이다.

## Collection
순서나 집합적인 저장공간

### Set
순서를 유지하지 않는 데이터의 집합으로 데이터의 중복을 허용하지 않는다.

#### HashSet
- **가장 빠른 임의 접근 속도**
- 순서를 예측할 수 없다.

#### TreeSet
- **정렬 방법을 지정**할 수 있다.

### List
순서가 있는 데이터의 집합으로 데이터의 중복을 허용한다.

#### Vector
- 과거에 대용량 처리를 위해 사용했다.
- 내부에서 자동으로 **동기화 처리**가 일어난다.
- 비교적 **성능이 좋지 않고 무거워** 잘 쓰이지 않는다.

#### ArrayList
- 단방향 포인터 구조로 각 데이터에 대한 인덱스를 가지고 있어** 조회 기능**에 성능이 뛰어나다.

#### LinkedList
- 양방향 포인터 구조로 데이터의 **삽입, 삭제**가 빈번할 경우 데이터의 위치 정보만 수정하면 되기에 유용하다.
- 스택, 큐, 양방향 큐 등을 만드는 용도로 쓰인다.

## Map
키와 값으로 이루어진 데이터의 집합으로 순서는 유지되지 않으며 키의 중복을 허용하지 않으니 값의 중복은 허용한다.

### Hashtable
- HashMap 보다는 느리지만 **동기화를 지원**한다.
- null 값이 올 수 없다.

### HashMap
- 중복과 순서가 허용되지 않는다.
- null 값이 올 수 있다.

### TreeMap
- **정렬된 순서대로 키와 값을 저장**하여 검색이 빠르다.

출처 : https://gangnam-americano.tistory.com/41

## Java의 메모리 영역
1. 메소드 영역 : Byte 코드, 전역 변수, Static 변수
2. 스택 영역 : 매개 변수, 지역 변수 -> 컴파일 시 메모리에 할당되며 사용이 끝나면 바로 소멸한다.
3. 힙 영역 : new 로 생성된 객체 -> 호출이 끝나도 사라지지 않으며 프로그램 실행 시 동적으로 할당된다.

## 접근 제어자
1. public : 접근 제한이 없다.
2. protected : 같은 패키지 내, 다른 패키지의 자손 클래스에서 접근이 가능하다.
3. default : 같은 패키지 내에서만 접근이 가능하다.
4. private : 같은 클래스 내에서만 접근이 가능하다.

## Abstract와 Interface

### Abstract
- 추상메소드를 하나 이상 가진 클래스
- 자신의 생성자로 객체 생성이 불가능하다.
- 일반 메소드를 사용할 수 있다.

### Interface
- 추상 메소드와 상수만으로 이루어진 추상 클래스
- 다중 상속이 가능하다.
- 메소드의 선언만 가능하다.

### Interface 사용 이유
**팀 작업에서 공동 작업 시 충동을 방지하기 위해서**이다. A는 클래스를 개발하고, B는 그 클래스를 이용하여 코드를 개발해야 할 때, 인터페이스가 구현되어 있다면 B는 그 결과값을 알기 대문에 A가 클래스를 개발할때까지 기다릴 필요가 없이 작업을 시작할 수 있다.

## Serialization
- JVM 힙 영역에 존재하는 객체를 한 줄로 늘어선 바이트의 형태(Stream)로 만드는 것을 직렬화라고 한다.
  - 자바에서는 파일이나 콘솔의 입출력을 직접 다루지 않고, 스트림이라는 흐름을 통해 다룬다.
  - ex) 프로그램 <-> 스트림 <-> 키보드, 모니터, 파일, 네트워크, ...
- 직렬화한 것을 객체의 형태로 복원하는 작업을 역직렬화라고 한다.

예시 : https://github.com/BinSin/BinSinMall/blob/master/binsinHibernateStore/src/main/java/com/binsin/store/model/Cart.java

## Process vs Thread
- Process
  - **실행 중인 프로그램**이다. 프로그램을 실행하면 OS로부터 실행에 필요한 자원을 할당받아 프로세스가 된다.
- Thread
  - **프로세스의 자원을 이용하여 실제로 작업을 수행하는 것**이다.

### Thread를 구현하는 방법
1. Thread Class를 상속받는다.
2. Runnable 인터페이스를 implements하여 구현한다.

## Static
- 인스턴스를 생성하면, 각 인스턴스들은 서로 독립적이기 때문에 서로 다른 값을 유지하는데, static을 사용하면 **각 인스턴스들이 공통적으로 값이 유지**된다.
- static이 붙은 멤버변수는 **클래스가 메모리에 올라갈때 자동적으로 생성**되기 때문에 인스턴스를 생성하지 않아도 된다.
- 덕분에 **메서드의 호출시간이 짧아지기 때문에 효율이 높아진다.**
- 따라서 클래스의 멤버변수 중 **모든 인스턴스에 공통된 값을 유지해야 하는 경우**, 작성한 메서드 중에서 **인스턴스 변수를 사용하지 않는 메서드**에 static을 붙여준다.

출처 : https://vaert.tistory.com/101

### Static 단점

- 객체 지향적이지 않다. 객체의 데이터를 **캡슐화해야 하는데 static을 사용하면 이 법칙에 위배**된다.
- 지나치게 많은 static 변수를 사용하게 되면 이들로부터 **프로그램이 종료할 때까지 메모리를 회수할 수 없기 때문에 가상머신이 메모리 부족**을 겪게 된다.
- interface를 구현할 때 static 메서드를 사용할 수 없다. 이렇게** 재사용성을 높여주는 자바의 유용한 객체지향적 기능들을 사용하는 것을 방해**한다.

출처 : https://unabated.tistory.com/entry/%EC%99%9C-%EC%9E%90%EB%B0%94%EC%97%90%EC%84%9C-static%EC%9D%98-%EC%82%AC%EC%9A%A9%EC%9D%84-%EC%A7%80%EC%96%91%ED%95%B4%EC%95%BC-%ED%95%98%EB%8A%94%EA%B0%80



## Call by Reference vs Call by Value
- Call by Reference : 매개 변수의 원래 **주소에 값을 저장**하는 방식
- Call by Value : 주어진 **값을 복사하여 처리**하는 방식, 메소드 내의 처리 결과는 메소드 밖의 변수에 영향을 미치지 않는다.

## Primitive type vs Reference type
- Primitive type : 변수에 **값 자체를 저장**하는 것
- Reference type : 메모리 상에 **객체가 있는 위치를 저장**하는 것

## Generic
제네릭은 **코드 블럭 내부에서 쓸 자료형을 외부에서 지정하는 기법**을 뜻한다. 여러가지 자료형을 허용하고 싶을 때 Object로 선언해버리면 깔끔하지만, 그렇게하면 **원하지 않는 자료형이 입력되었을 때의 오류를 컴파일 시점에 잡아낼 수 없다.**

### Generic Class
클래스 내부에서 사용될 자료형을 지정할 수 있다.
```Java
class Foo<T> {
    private T t;

    public void set(T t) {
        this.t = t;
    }

    public T get() {
        return t;
    }
}
```

### Generic Method
메소드에만 제네릭을 선언할 수 있다. 이 때 파라미터 타입 또는 리턴 타입에 제네릭을 선언했으면 **메소드의 리터나입 앞에도 똑같이 선언**해 주어야 한다.
```Java
class Koo {
    // 두개 이상의 파라미터에도 각각 제네릭을 설정할 수 있다.
    public <N1, N2> Integer exampleOne(N1 t, N2 e) {
        return (Integer)t + (Integer)e;
    }

    // 먼저 나왔던 Foo 클래스를 리턴타입으로 정의한 메소드
    public <String> Foo<String> exampleTwo() {
        return new Foo<>();
    }
}
```

## Generic Interface
제네릭을 선언하여 클래스들이 인터페이스 구현을 유연하게 할 수 있다.
```Java
interface Roo <T1, T2, T3> {
    T1 implementThis(T1 t1);
    T2 implementThis();
    T3 maintainGeneric(T3 t3);
}

// 제네릭에 어떤 자료형의 정의하느냐에 따라 유연하게 구현 가능.
class roo <String, Integer, T3> implements Roo<String,Integer,T3> {

    @Override
    public String implementThis(String s) {
        return s;
    }

    @Override
    public Integer implementThis() {
        return null;
    }

    // 이렇게 제네릭을 유지하는 방법도 있음.
    @Override
    public T3 maintainGeneric(T3 t3) {
        return null;
    }
}
```

출처: https://preamtree.tistory.com/138

## Wrapper Class
- 기본 자료형(Primitive type)의 데이터를 객체로 만들기 위해 포장하는 클래스이다.

### 사용 이유
- 제네릭, 자료구조, 매개변수 등 **기본 자료형이 아닌 래퍼런스 타입을 필요로 하는 경우**가 많고 **메서드를 갖고 있어 다양하게 활용이 가능**하기 때문이다.

### Boxing vs Unboxing
- Boxing :  박싱(boxing)은 기본 자료형의 데이터를 래퍼(wrapper) 클래스의 객체로 만드는 과정
- Un-Boxing : 래퍼(wrapper) 클래스의 데이터를 기본 자료형으로 얻어내는 과정
- new 연산자 또는 valueOf() 메소드를 이용할 수 있다.

출처 : http://blog.naver.com/PostView.nhn?blogId=heartflow89&logNo=220975218499&redirect=Dlog&widgetTypeCall=true

## String vs StringBuffer vs StringBuilder
- String
  - 한번 생성되면 변경이 불가능하다. (immutable)
  - 만약 문자열에 변화를 주면 메모리 공간이 변하는 것이 아니라 **새로운 String 객체**를 만들어서 새로운 메모리 공간을 만든다.
  - 기존의 문자열은 Garbage Collector에 의해 제거되기 때문에 **문자열 연산이 많아지게 되면 오버헤드가 발생**하여 성능이 떨어진다.
  - 따라서 **문자열 연산이 적고 조회가 많을 때 사용**하는 것이 좋다.
- StringBuffer
  - 변경이 가능하다. (mutable)
  - 멀티 쓰레드 환경에서 synchronized 키워드가 가능하므로 동기화가 가능하다. (Thread-Safe)
  - 따라서 **문자열 연산이 많은 멀티 쓰레드 환경에 적절**하다.
- StringBuilder
  - 변경이 가능하다. (mutable)
  - 동기화를 지원하지 않기 때문에 멀티 쓰레드 환경에 적절하지 않다.
  - 따라서 **싱글쓰레드 또는 쓰레드를 사용하지 않아도 되는 환경에 적절**하다.

## Java8 버전 추가 기능

### Lambda Function
람다는 익명 함수이고, 함수를 정의하는 간편한 방법이다.

#### 장단점
- 장점
  1. **코드를 간결**하게 만들 수 있습니다.
  2. 코드가 간결하고 식에 개발자의 의도가 명확히 드러나므로 **가독성이 향상**됩니다.
  3. 함수를 만드는 과정없이 한번에 처리할 수 있기에 코딩하는 **시간이 줄어**듭니다.
  4. **병렬프로그래밍이 용이**합니다.

- 단점
  1. 람다를 사용하면서 만드는 **무명함수는 재사용이 불가능**합니다.
  2. **디버깅이 다소 까다**롭습니다.
  3. 람다를 **남발하면 코드가 지저분**해질 수 있습니다. (비슷한 함수를 계속 중복생성할 가능성이 높음)
  4. **재귀로 만들경우에는 다소 부적합**한면이 있습니다.

출처 : https://coding-factory.tistory.com/265

#### 기본 문법
```Java
// Arrays.sort() 와 익명 클래스
Arrays.sort(numbers, new Comparator<Integer>() {
  @Override
  public int compare(Integer first, Integer second) {
    return first.compareTo(second);
  }
});

// 인스턴스 생성과 메소드 시그니처를 간략화
Arrays.sort(numbers, (Integer first, Integer second) {
  return first.compareTo(second);
});

// 인자의 타입을 생략하고 중괄호를 삭제해 간략화
Arrays.sort(numbers, (first, second) -> first.compareTo(second));
```
람다는 기본적으로 기능을 가지는 익명의 코드 블록입니다. 위 예제에서 보면 람다를 이용해 훨씬 간결하게 표현한 것을 볼 수 있습니다. 여기서 람다가 Comparator<Integer> 타입으로 처리됩니다. Comparator 는 **하나의 추상 메소드만 가지고 있기 때문에**, 컴파일러가 봤을 때 이 람다가 그 추상 메소드를 구현한 내용이라고 보고 Comparator<Integer> 타입으로 처리한 것입니다.

이렇게 언제든지 **하나만 있는 추상 메소드는 람다로 교체할 수 있습니다.**

#### FunctionalInterface
FunctionalInterface는 오직 하나의 선언을 갖는 인터페이스로 원래 인터페이스는 메소드의 **선언**만 할 수 있지만 FunctionalInterface의 등장으로 **구현**도 할 수 있게 되었다.

```Java
@FunctionalInterface
interface MyCalc {
// 하나의 메소드 선언
}
```

#### 문법 요약
```Java
// 인자 -> 바디
(int x, int y) -> { return x + y; }

// 인자 타입 생략 - 컴파일러가 추론
(x, y) -> { return x + y; }

// return 및 중괄호 생략
(x, y) -> x + y

// 인자가 하나인 경우 인자 괄호 생략
x-> x * 2

// 인자가 없으면 빈 괄호로 표시
() -> System.out.println("Hey there!")

// 메소드 참조 Method reference
// (value -> System.out.println(value)) 의 축약형
System.out::println
```

출처 : https://futurecreator.github.io/2018/07/19/java-lambda-basics/

### Stream
자바 8에서 추가한 스트림(Streams)은 람다를 활용할 수 있는 기술 중 하나입니다. 자바 8 이전에는 배열 또는 컬렉션 인스턴스를 다루는 방법은 for 또는 foreach 문을 돌면서 요소 하나씩을 꺼내서 다루는 방법이었습니다. 간단한 경우라면 상관없지만 로직이 복잡해질수록 코드의 양이 많아져 여러 로직이 섞이게 되고, 메소드를 나눌 경우 루프를 여러 번 도는 경우가 발생합니다.

스트림은 '데이터의 흐름’입니다. 배열 또는 컬렉션 인스턴스에 함수 여러 개를 조합해서 원하는 결과를 필터링하고 가공된 결과를 얻을 수 있습니다. 또한 람다를 이용해서 코드의 양을 줄이고 간결하게 표현할 수 있습니다. 즉, 배열과 컬렉션을 함수형으로 처리할 수 있습니다.

또 하나의 장점은 간단하게 병렬처리(multi-threading)가 가능하다는 점입니다. 하나의 작업을 둘 이상의 작업으로 잘게 나눠서 동시에 진행하는 것을 병렬 처리(parallel processing)라고 합니다. 즉 쓰레드를 이용해 많은 요소들을 빠르게 처리할 수 있습니다.

스트림에 대한 내용은 크게 세 가지로 나눌 수 있습니다.

생성하기 : 스트림 인스턴스 생성.
가공하기 : 필터링(filtering) 및 맵핑(mapping) 등 원하는 결과를 만들어가는 중간 작업(intermediate operations).
결과 만들기 : 최종적으로 결과를 만들어내는 작업(terminal operations).

```
전체 -> 맵핑 -> 필터링 1 -> 필터링 2 -> 결과 만들기 -> 결과물
```

출처 : https://futurecreator.github.io/2018/08/26/java-8-streams/

#### 장점
불필요한 코딩(for, if 문법)을 걷어낼 수 있고 직관적이기 때문에 가독성이 좋아진다.

#### 사용법
1. 스트림 생성
2. 중개 연산
3. 최종 연산

```
Collections 같은 객체 집합.스트림생성().중개연산().최종연산();
```
**.** 으로 연계할 수 있는 방법인 파이프라인

##### 중개 연산
람다 식으로 처리할 수 있다.

###### Filter
조건에 맞는 것만 거른다.
```Java
List<String> names = Arrays.asList("jeong", "pro", "jdk", "java");
Stream<String> a = names.stream().filter(x -> x.contains("o")); // o를 포함한 문자열 반환
```

###### Map
각 요소를 연산하는데 쓰인다.
```Java
List<String> names = Arrays.asList("jeong", "pro", "jdk", "java");
names.parallelStream().map((x) ->{return x.concat("s");}).forEach(x -> System.out.println(x)); // 각 문자열에 뒤에 s 붙인다.
```

###### Sorted
정렬

###### Limit
개수 제한
```Java
List<Integer> ages = Arrays.asList(1,2,3,4,5,6,7,8,9);
ages.stream().filter(x -> x>3)).limit(3); // 스트림의 개수를 3개로 제한
```

###### Distinct
중복 제거

###### Skip
.skip(3) 이라고 하면 처음 3개의 요소를 제외

###### mapToInt, mapToLong, mapToDouble
해당 타입의 스트림으로 바꿔준다. 예를 들어 "1", "2", "3" 을 mapToInt를 적용하면 1, 2, 3을 가진 스트림으로 변환 해준다.


##### 최종 연산
###### count(), min(), max(), sum(), average()
갯수, 최소값, 최대값, 합계, 평균을 얻을 수 있는 함수

###### reduce
누적된 값을 계산하는 함수.
```Java
List<Integer> ages = new ArrayList<Integer>();
ages.add(1);ages.add(2);ages.add(3);//1,2,3
System.out.println(ages.stream().reduce((b,c) -> b+c).get()); // 1+2+3=6 이 출력된다.
```

###### forEach
각 요소를 돌면서 처리
```Java
List<Integer> ages = new ArrayList<Integer>();
ages.add(1);ages.add(2);ages.add(3);//1,2,3
Set<Integer> set = ages.stream().collect(Collectors.toSet());
set.forEach(x-> System.out.println(x));//1,2,3
```

###### collect
스트림의 값들을 모아준다.

###### iterator
Iterator<T>를 반환한다.

###### noneMatch, anyMatch, allMatch
조건을 **모든 요소들이 만족하는지 않는지**, ** 하나라도 조건을 만족**하는지, **모든 요소들이 만족**하는지 판단해서 boolean 값을 리턴한다.
```Java
List<Integer> ages = new ArrayList<Integer>();
ages.add(1);ages.add(2);ages.add(3);//1,2,3
System.out.println(ages.stream().filter(x -> x>1).noneMatch(x->x>2));//false
```

##### 주의점
- Stream은 **재사용이 불가능**한다.
- 병렬 스트림은 여러 쓰레드가 작업한다. -> paralleStream()
- 중개 연산은 **미리하지 않고 최종 연산이 적용될 때 중개 연산도 실행**된다.

출처: https://jeong-pro.tistory.com/165

## Exception
예외는 try/catch 로 사전에 예방할 수 있다.

### Error vs Exception
컴퓨터 하드웨어의 오작동 또는 고장으로 인해 응용프로그램 실행 오류가 발생하는 것을 자바에서는 에러(Error)라고 하고, 에러는 메모리 부족이나 스택오버플로우와 같이 일단 발생하면 복구할 수 없는 심각한 오류이고, 예는 발생하더라도 수습될 수 있는 비교적 덜 심각한 것이다.

에러는 JVM 실행에 문제가 생긴 것이므로 개발자가 대처할 방법이 없다. 하지만 예외(Exception)는 사용자의 잘못된 조작 또는 개발자의 잘못된 코딩으로 인해 발생하는 프로그램 오류를 말한다.

예외가 발생되면 프로그램은 곧바로 종료된다는 점에서는 에러와 동일하다. 그러나 예외는 예외처리를 통해 프로그램을 종료하지 않고 정상 실행 상태가 유지되도록 할 수 있다.

### Runtime Exception
- NullPointerException : 객체 참조가 없는 상태일 경우 발생한다.
- ArrayIndexOutOfBoundsException : 배열에서 인덱스 범위를 초과하여 사용할 경우인 에러이다.
- NumberFormatExcpeion : 문자열로 되어 있는 데이터를 숫자로 변경하는 경우 발생한다.
- ArithmeticException : 어떤 수를 0으로 나눌 때 발생한다.
- ClassCastException : 적절치 못하게 클래스를 형변환하는 경우 에러가 발생한다.
- OutOfMemoryException : 사용 가능한 메모리가 없는 경우에 발생한다.
- NoClassDefFoundException : 원하는 클래스를 찾지 못한 경우에 발생한다.
- NegativeArraySizeException : 배열의 크기가 음수값인 경우 발생한다.

출처 : https://deftkang.tistory.com/44
