# Spring Security 
<br>

-----------------------

### Security Filter Chain이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />

+ Spring Security의 웹 인프라 구조는 일반 서블릿 필터에 온전히 기반하고 있습니다. <br>
  Spring Security는 내부적으로 서블릿 혹은 다른 서블릿 기반한 프레임워크를 사용하지는 않으므로, <br>
  특정 웹 기술에 대한 강한 연결은 없습니다. <br>
  Spring Security는 HttpServletRequest나 HttpServletResponse를 다루며,<br>
  요청이 브라우저, 웹 서비스 클라이언트, HttpInvoker 혹은 AJAX 애플리케이션 어느 곳에서 오던지 상관 없습니다.<br>
  
  Spring Security는 내부적으로 filter chain을 유지하고, 서비스의 필요에 따라 각각의 filter는 추가되거나 삭제됩니다. <br>
  필터의 순서는 중요한데, 그 이유는 그것들 사이에 종속성이 존재하기 때문입니다. <br>
  
  https://docs.spring.io/spring-security/site/docs/3.1.4.RELEASE/reference/security-filter-chain.html
  
</details>

-----------------------

