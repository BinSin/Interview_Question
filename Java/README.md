# Java
- [Abstract / Interface](#abstract와-intercae)
  - Interface
  - Abstract
  - Interface 사용 이유
- [Java8 버전 추가 기능](#java8-버전-추가-기능)
  - [Lambda Function](#lambda-function)
    - [장단점](#장단점)
    - [기본 문법](#기본-문법)
    - [문법 요약](#문법-요약)
  - [Stream]

## Abstract와 Interface



##Java8 버전 추가 기능

### Lambda Function
람다는 익명 함수이고, 함수를 정의하는 간편한 방법이다.

#### 장단점
- 장점
  1. 코드를 간결하게 만들 수 있습니다.
  2. 코드가 간결하고 식에 개발자의 의도가 명확히 드러나므로 가독성이 향상됩니다.
  3. 함수를 만드는 과정없이 한번에 처리할 수 있기에 코딩하는 시간이 줄어듭니다.
  4. 병렬프로그래밍이 용이합니다.

- 단점
  1. 람다를 사용하면서 만드는 무명함수는 재사용이 불가능합니다.
  2. 디버깅이 다소 까다롭습니다.
  3. 람다를 남발하면 코드가 지저분해질 수 있습니다. (비슷한 함수를 계속 중복생성할 가능성이 높음)
  4. 재귀로 만들경우에는 다소 부적합한면이 있습니다.

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

이렇게 언제든지 하나만 있는 추상 메소드는 람다로 교체할 수 있습니다.

### 문법 요약
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
