# Java
- [Java의 특징](#java의-특징)
- [객체 지향 프로그래밍](#객체-지향-프로그래밍)
  - [OOP의 특징](#oop의-특징)
  - [Object](#object)
  - [Overloading vs Overriding](#overloading-vs-overriding)
- [Abstract와 Interface](#abstract와-intercae)
  - [Interface](#interface)
  - [Abstract](#abstract)
  - [Interface 사용 이유](#interface-사용-이유)
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

## Java의 특징
1. 자바는 네트워크 상에서 쓸 수 있도록 개발한 **객체 지향 프로그래밍 언어**이다.
2. **Java Virtual Machine**만 설치하면 컴퓨터의 OS에 상관없이 작동한다. (즉, **운영체제에 독립적**이다.)
3. 기본 자료형을 제외한 모든 요소들이 **객체로 표현 가능**하다.
4. 객체 지향 개념의 특징인 **캡슐화, 상속성, 다형성**이 잘 적용된 언어이다.
5. **Garbage Collector를 통한 자동적인 메모리 관리**가 가능하다.
6. **멀티쓰레드**를 지원한다.

## 객체 지향 프로그래밍
- 실제 세계의 데이터를 객체로 취급하여 그 객체와의 상호작용을 통해 프로그램이 동작하는 것을 말한다.

### OOP의 특징
1. **코드의 재사용성**이 높다.
2. **코드의 관리가 용이**하여 쉽게 코드를 변경할 수 있다.
3. 제어자와 메서드를 이용하여 데이터를 보호하고, 코드의 중복으르 제거함으로써 **신뢰성이 높은 프로그래밍**을 가능하게 한다.

### Object
- 객체는 객체 지향 프로그래밍에서 데이터와 그 데이터에 관련되는 동작을 모두 포함한 개념이다.

### Overloading vs Overriding
- Overloading
  - 클래스 내에 **같은 이름의 메소드를 여러 개 정의하는 것**이다.
  - 매개변수의 타입이 다르거나 개수가 달라야 한다.

- Overriding
  - **부모 클래스의 메소드를 하위 클래스에서 상속받아 재정의하는 것**이다.

## Abstract와 Interface

### Interface


### Abstract


# Interface 사용 이유



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
