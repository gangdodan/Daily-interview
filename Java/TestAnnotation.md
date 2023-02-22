## class annotation
#### @SpringBootTest
- @SpringBootTest는 전체 스프링 애플리케이션 컨텍스트를 로드하며 모든 빈을 생성한다. -> 애플리케이션의 실제 동작을 테스트할 수 있다. 
- @SpringBootTest를 사용하면 모든 빈을 로드하기 때문에 테스트 환경에서 애플리케이션이 잘 동작하는지 더욱 정확하게 확인할 수 있지만 애플리케이션의 동작을 테스트하기 때문에 테스트 시간이 느리다는 단점이 있다.

#### @WebMvcTest
- @WebMvcTest는 스프링 MVC 컨트롤러를 테스트하기 위한 애노테이션이며 애플리케이션의 일부분인 웹 계층(Web Layer)만 로드되므로 더 빠른 테스트가 가능하다. 
- @WebMvcTest에서는 웹 계층에서 사용되는 빈들만 로드하기 때문에 테스트가 더욱 직관적이고 간단하지만 서비스 계층(Service Layer)이나 데이터 액세스 계층(Data Access Layer)에서 발생하는 문제는 테스트할 수 없다.

따라서, @SpringBootTest는 애플리케이션의 전반적인 동작을 테스트하는 통합 테스트에, @WebMvcTest는 스프링 MVC 컨트롤러의 동작을 테스트하는 단위 테스트에 사용한다.

#### @ExtendWith
