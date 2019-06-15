# Spring
- [Framework를 사용하는 이유](#framework를-사용하는-이유)
- [Library vs Framework](#library-vs-framework)
  - Library
  - Framework
- [Web Server vs Web Application Server](web-server-vs-web-appliccation-server)
  - Web Server
  - Web Application Server(WAS)
  - Web Server와 WAS가 필요한 이유
- [Servlet vs JSP](#servlet-vs-jsp)
  - Servlet
  - JSP
  - Servlet과 JSP의 관계
    - JSP만 이용하는 모델
    - JSP와 Servlet을 모두 이용하는 모델 (MVC)
- [Spring Framework](#spring-framework)
  - Spring의 정의
  - Spring의 전략
  - Spring의 특징
  - Spring Framework의 기능요소

## Framework를 사용하는 이유
소프트웨어의 설계와 구현에 있어서 **전체적인 뼈대와 틀을 제공**함으로써 개발자가 편하게 개발할 수 있게 해준다. 프레임워크의 사용으로 개발자는 비즈니스 로직에 집중함으로써 **생산성이 증가**하고 코드의 재사용성, 유지 보수성 그리고 확장성을 갖게 해줌으로서 **코트의 품질을 높여**준다.

## Library vs Framework
중요한 차이점은 **제어의 역전**이다.

### Library
- 클래스의 집합으로서 코드의 **재사용성을 지원**해 준다. (예를 들면 Math 함수)
- 제어의 주체는 **개발자 자신**으로 코드에서 라이브러리 함수를 호출하여 사용한다.

### Framework
- 제어의 주체가 **프레임워크**가 되어 프레임워크에서 우리의 코드를 호출한다. (IOC; Inversion of Control)
- 프레임워크에서 기본적인 뼈대를 잡아놓았기 때문에 우리는 **제어의 흐름에 맞게 코드를 작성**해 주면 프레임워크에서 그것에 맞게 호출한다.

## Web Server vs Web Application Server

### Web Server
- 웹 프라우저 클라이언트로부터 HTTP 요청을 받아 정적인 컨텐츠를 제공하는 컴퓨터 프로그램
- **정적**인 컨텐츠를 제공한다.
- WAS를 거치지 않고 **바로 자원을 제공**한다.
- Web Server에서는 정적 컨텐츠만 처리하도록 기능을 분배하여 **서버의 부담을 줄일 수 있다.**
- Ex) Apache Server, Nginx, IIS 등

### Web Application Server
- DB 조회나 다양한 로직 처리를 요구하는 **동적**인 컨텐츠를 제공하기 위해 만들어진 Application Server
- HTTP를 통해 컴퓨터나 장치에 애플리케이션을 수행해주는 미들웨어이다.
- WAS를 통해 요청에 맞는 데이터를 DB에서 가져와서 비즈니스 로직에 맞게 결과를 만들어 제공함으로써 **자원을 효율적으로 사용**할 수 있다.
- Ex) Tomcat, JBoss, Jeus 등

출처 : https://gmlwjd9405.github.io/2018/10/27/webserver-vs-was.html

### Web Server와 WAS를 구분하는 이유
- **서버의 자원을 효율적으로 사용하자** 에서 출발한다.
- 사용자가 원하는 요청에 대한 결과값을 모두 만들어놓고 서비스하기엔 절대적으로 **자원이 부족**하다.
- 클라이언트에게 이미지 파일과 같은 정적인 파일들을 보내줄 때, HTML 문서가 보내질 때 함께 가는 것이 아니고 클라이언트가<U> HTML 파일을 먼저 받고 그에 필요한 이미지 파일들을 다시 서버로 요청하면 그때 보내준다.</U>
- 이 때, 우리의 서버는 데이터베이스를 왔다갔다 하며 로직을 처리하기 바쁜데, 단순한 정적 파일을 브라우저에게 돌려주는 역할을 한다면 굉장히 비효율 적이다.
- 따라서 이 둘을 나누어 처리하면 더욱 **효율적으로 자원을 활용**할 수 있다.

출처 : https://dodo4513.github.io/2017/06/18/server_architecture/

## Servlet vs JSP

### Servlet
- Java 언어를 웹어플리케이션 개바하기 쉽게 하기 위해 만든 API이며 이 규약에 맞는 라이브러리나 클래스들을 상속 및 구현하여 만든 클래스들을 Servlet 이라고 한다.
- **Java 코드** 안에 HTML 코드가 있다.
- **데이터 처리(Controller)** 에 좋다.
- 즉, DB와의 통신, Business Logic 호출, 데이터 읽고 확인하는 작업에 유용하다
- Servlet이 수정되면 Java 코드를 컴파일(.class 파일 생성)한 후 동적인 페이지를 처리하기 때문에 전체 코드를 업데이트하면 다시 컴파일한 후 재배포하는 작업이 필요하다. (**개발 생산성 저하**)

### JSP
- HTML 코딩이 어렵고 불편해서 HTML 내부에 **Java 코드를 삽입하는 형식**
- **HTML 코드** 안에 Java 코드가 있다.
- **Presentation(View)** 에 좋다.
- 즉, 요청 결과를 나타내는 HTML을 작성하는데 유용하다.
- JSP가 수정된 경우 재배포할 필요가 없이 WAS가 알아서 처리한다. (배포가 쉽다)

### Servlet과 JSP의 관계

#### JSP만을 이용하는 모델
- JSP가 사용자의 요청을 받아 Java Bean(DTO, DAO)을 호출하여 적절한 동적 페이지를 생성한다.
- 장점 : 개발 속도가 빠르고 배우기 쉽다.
- 단점 : View와 Controller가 혼재(디자인과 로직이 섞임)하여 코드가 복잡해져 **유지 보수가 어려워**진다.

#### JSP와 Servlet을 모두 이용하는 모델 (MVC)
- JSP와 Servlet을 모두 사용하여 View와 Controller를 분리한다.
- **Model(Java Beans)** : 에플리케이션의 상태(데이터)를 나타낸다.
- **View(JSP)** : 보여지는 부분을 책임진다.
- **Controller(Servlet)** : Model과 View 사이의 **인터페이스 역할**을 한다.
- 장점 : 기능에 따라 코드가 분리되어 있기 때문에 **유지보수가 용이**하다.
- 단점 : 구조가 복잡하여 습득이 어렵고 작업량이 많다.

출처 : https://gmlwjd9405.github.io/2018/11/04/servlet-vs-jsp.html

## Spring Framework

### Spring의 정의
- IoC와 AOP를 지원하는 경량의 컨테이너 프레임워크

### Spring의 전략
- Portable Service Abstraction(서비스 추상화) : 기술적인 복잡함은 추상화를 통해 Low Level의 기술구현부분과 기술을 사용하는 **인터페이스로 분리**한다.
- DI(Dependency Injection) : 유연하게** 확장 가능한 객체**를 만들어 두고 그 관계는 외부에서 동적으로 설정해준다.
- AOP(Aspect Oriented Programming) : 애플리케이션 로직을 담당하는 코드에 남아있는 기술 관련 코드를 분리해서** 별도의 모듈로 관리**할 수 있게 해준다.
- POJO(Plain Old Java Object) : **객체지향 원리에 충실**하면서, 특정 환경이나 규약에 종속되지 않고 **필요에 따라 재활용될 수 있는 방식**으로 설계된 객체이다.

### Spring의 특징
- 경량 컨테이너로 자바 객체를 직접 관리한다.
- 제어의 역전(IoC : Inversion of Control)을 지원하여 필요에 따라 스프링에서 사용자의 코드를 호출한다.
- 의존성 주입(DI : Dependency Injection)을 지원하여 각각의 계층이나 서비스들 간에 의존성이 존재할 경우 프레임워크가 서로 연결해준다.
- 관점지향 프로그래밍(AOP : Aspect Oriented Programming)으로 트랜잭션, 로깅, 보안과 같은 여러 모듈에서 공통적으로 사용하는 기능의 경우 해당 기능을 분리하여 관리한다.
- POJO(Plain Old Java Object) 방식의 프레임워크로 기존에 존재하는 라이브러리의 지원이 용이하다.
- 트랜잭션 처리를 위한 일관된 방법을 지원
- 영속성과 관련된 다양한 서비스를 지원하여 Mybatis, hibernate 등과 같은 데이터베이스 처리 라이브러리와 연결할 수 있는 인터페이스를 제공한다.
- 높은 확장성을 갖는다.

### Spring Framework의 기능요소(모듈)
- Spring Core : Spring 프레임워크의 기본기능을 제공한다. 이 모듈에 있는 BeanFactory는 Spring의 기본 컨테이너이면서 스프링 DI 기반이다.
- Spring Context : BeanFactory의 개념을 확장한 것으로 국제화 메시지, 애플리케이션 생명주기 이벤트, 유효성 검증을 지원한다.
- Spring DAO : JDBC에 대한 추상화 계층으로 JDBC 코딩이나 예외처리 하는 부분을 간편화 시켰으며, AOP 모듈을 이용해 트랜잭션 관리 서비스도 제공한다.
- Spring ORM : Mybatis, Hibernate, JPA 등 널리 사용되는 ORM 프레임워크와의 연결고리를 제공한다.
- Spring AOP : AOP 모듈을 통해 관점 지향 프로그래밍을 지원한다.
- Spring Web : 일반적인 웹 애플리케이션 개발에 필요한 기본기능을 제공하고, Webwork나 Struts와 같은 다른 웹 애플리케이션 프레임워크와의 통합을 지원한다.
- Spring Web MVC : 사용자 인터페이스가 애플리케이션 로직과 분리되는 웹 애플리케이션을 만드는 경우에 사용되는 일반적인 예시이다.

출처 : https://shlee0882.tistory.com/200
