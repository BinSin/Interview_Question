# Spring Framework
- [Framework를 사용하는 이유](#framework를-사용하는-이유)
- [Library vs Framework](#library-vs-framework)
  - Library
  - Framework
- [Servlet vs JSP](#servlet-vs-jsp)
  - Servlet
  - JSP
  - Servlet과 JSP의 관계
    - JSP만 이용하는 모델
    - JSP와 Servlet을 모두 이용하는 모델 (MVC)
- [Spring의 장점](#spring의-장점)

## Framework를 사용하는 이유
소프트웨어의 설계와 구현에 있어서 전체적인 뼈대와 틀을 제공함으로써 개발자가 편하게 개발할 수 있게 해준다. 프레임워크의 사용으로 개발자는 비즈니스 로직에 집중함으로써 생산성이 증가하고 코드의 재사성, 유지 보수성 그리고 확장성을 갖게 해줌으로서 코트의 품질을 높여준다.

## Library vs Framework
중요한 차이점은 '제어의 역전'이다.

### Library
- 클래스의 집합으로서 코드의 재사용성을 지원해 준다. (예를 들면 Math 함수)
- 제어의 주체는 나 자신으로 코드에서 라이브러리 함수를 호출하여 사용한다.

### Framework
- 제어의 주체가 프레임워크가 되어 프레임워크에서 우리의 코드를 호출한다. (IOC; Inversion of Control)
- 프레임워크에서 기본적인 뼈대를 잡아놓았기 때문에 우리는 제어의 흐름에 맞게 코드를 작성해 주면 프레임워크에서 그것에 맞게 호출한다.

## Servlet vs JSP

### Servlet
- **Java 코드** 안에 HTML 코드가 있다.
- **데이터 처리(Controller)**에 좋다.
- 즉, DB와의 통신, Business Logic 호출, 데이터 읽고 확인하는 작업에 유용하다
- Servlet이 수정되면 Java 코드를 컴파일(.class 파일 생성)한 후 동적인 페이지를 처리하기 때문에 전체 코드를 업데이트하면 다시 컴파일한 후 재배포하는 작업이 필요하다. (**개발 생산성 저하**)

### JSP
- **HTML 코드** 안에 Java 코드가 있다.
- **Presentation(View)**에 좋다.
- 즉, 요청 결과를 나타내는 HTML을 작성하는데 유용하다.
- JSP가 수정된 경우 재배포할 필요가 없이 WAS가 알아서 처리한다. (배포가 쉽다)

### Servlet과 JSP의 관계

#### JSP만을 이용하는 모델
- JSP가 사용자의 요청을 받아 Java Bean(DTO, DAO)을 호출하여 적절한 동적 페이지를 생성한다.
- 장점 : 개발 속도가 빠르고 배우기 쉽다.
- 단점 : Viewㅇ와 Controller가 혼재하여 코드가 복잡해져 유지 보수가 어려워진다.

#### JSP와 Servlet을 모두 이용하는 모델 (MVC)
- JSP와 Servlet을 모두 사용하여 View와 Controller를 분리한다.
- View(보여지는 부분) : HTML이 중심이 되는 JSP를 사용
- Controller(다른 자바 클래스에 데이터를 넘겨주는 부분) : Java 코드가 중심이 되는 Servlet을 사용
- Model(Java Beans) : DTO와 DAO를 통해 DB에 접근

출처 : https://gmlwjd9405.github.io/2018/11/04/servlet-vs-jsp.html

## Spring의 장점
