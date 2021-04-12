#### Spring AOP
+ 언제 사용되는가?
  + 성능 검사
  + 트랜잭션 처리
  + 로깅
  + 예외 반환
  + 검증

```
실 예로, @Transactional, @Cache같은 애노테이션들은 AOP를 활용하여 동작하게 된다.
```

+ 구성요소
    + JoinPoint: 모듈의 기능이 삽입되어 동작할 수 있는 실행 가능한 특정 위치
    + PointCut: 어떤 클래스의 어느 JoinPoint를 사용할 것인지를 결정
    + Advice: 각 JoinPoint에 삽입되어져 동작할 수 있는 코드
    + Interceptor: InterceptorChain 방식의 AOP 툴에서 사용하는 용어로 주로 한개의 호출 메소드를 가지는 Advice
    + Weaving: PointCut에 의해서 결정된 JoinPoint에 지정된 Advice를 삽입하는 과정(CrossCutting)
    + Introduction: 정적인 방식의 AOP 기술
    + Aspect: PointCut + Advice + (Introduction)
   
 
+ Dependency
```
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>

<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-test</artifactId>
    <scope>test</scope>
</dependency>

<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-aop</artifactId>
</dependency>
  ```
+ PointCut && JoinPoint 
  | Pointcut | JoinPoints |
  | ----- | ----- |
  | execution(public * *(..)) | public 메소드 실행 |
  