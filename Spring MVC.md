# Spring MVC 
<br>

### Filter vs InterCeptor?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
 1) Filter란 J2EE 표준 스펙 기능으로, 디스패터 서블릿에 요청이 전달되기 전/후에 URL 패턴에 맞는 모든 요청에 대해 <br>
     부가적으로 처리할 수 있는 기능입니다. <br>
     디스패처 서블릿은 스프링의 가장 앞단에 존재하는 프론트 컨트롤러이므로, 필터는 스프링 밖에서 처리됩니다. <br> 
     즉, Filter는 Tomcat과 같은 웹 컨테이너에 의해 관리됩니다.<br>   
  
   
 2) Intercepter는 J2EE 표준 스펙인 Filter와 달리, 스프링이 제공하는 기술로서, 디스패처 서블릿이 컨트롤러를 호출하기 전과 후에<br>
     요청과 응답을 참조하거나 가공할 수 있는 기능을 제공합니다. <br> 
     즉, 웹 컨테이너에서 동작하는 Filter와는 달리 Interceptor는 스프링 컨텍스트에서 동작합니다. 
  
</details>

-----------------------

### DispatcherServlet이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
 - HTTP 요청 핸들러/컨트롤러를 위한 중앙 디스패처입니다. <br>
   등록된 핸들러에게 웹 요청을 처리하기 위해 보내는 역할을 하며, <br> 
   편리한 mapping과 exception handling 기능을 제공합니다. <br> 
  
</details>

-----------------------

### HandlerMapping이란?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
 - 요청과 handler object간의 mapping을 의미합니다. <br> 
  
</details>


-----------------------

### 스프링 MVC의 중심에는 무엇이 있는가?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
 [참고: 스프링 인 액션] 
 - 스프링 MVC의 중심에는 컨트롤러가 있으며, 이것은 웹 요청과 응답을 처리하는 컴포넌트입니다. <br> 
   
</details>


