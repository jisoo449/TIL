### filter chain 설정
- SpringSecurityFilterChain  
스프링 시큐리티를 사용할 때 SecurityConfig 설정을 SpringSecurityFilterChain에 추가하고 싶다면 SecurityConfig 클래스가 WebSecurityconfigurerAdapter를 상속하도록 설정하고, 클래스 위에 @EnableWebSecurity 어노테이션을 붙여준다.
    ```
    @Configuration
    @EnableWebSecurity //웹보안 활성화를위한 annotation
    public class SecurityConfig extends WebSecurityConfigurerAdapter {
        . . .
    }
    ```
- SecurityFilterChain 위치  
SecurityFilterChain이란 Spring Security의 구성 요소 중 하나로, 보안 필터 체인을 정의하는 역할을 한다. 즉, 보안 관련 요청을 처리하고 인증 및 인가를 수행한다.  
SecurityFilterChains은 WebSecurityConfigurerAdapter를 상속받은 구성 클래스인 SecurityConfig 또는 WebSecurityConfig에 위치시킬 수 있다.  
참고: https://docs.spring.io/spring-security/reference/servlet/architecture.html#servlet-securityfilterchain
