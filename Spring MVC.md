# Spring MVC 
<br>

### Filter vs InterCeptor?

<details>
   <summary> 답안 보기 (👈 Click)</summary>
<br />
+ 1) Filter란 J2EE 표준 스펙 기능으로, 디스패터 서블릿에 요청이 전달되기 전/후에 URL 패턴에 맞는 모든 요청에 대해 <br>
     부가적으로 처리할 수 있는 기능입니다. <br>
     디스패처 서블릿은 스프링의 가장 앞단에 존재하는 프론트 컨트롤러이므로, 필터는 스프링 밖에서 처리됩니다. <br> 
     즉, Filter는 Tomcat과 같은 웹 컨테이너에 의해 관리됩니다.  
  
   
+ 2) Intercepter는 J2EE 표준 스펙인 Filter와 달리, 스프링이 제공하는 기술로서, 디스패처 서블릿이 컨트롤러를 호출하기 전과 후에<br>
     요청과 응답을 참조하거나 가공할 수 있는 기능을 제공합니다. <br> 
     즉, 웹 컨테이너에서 동작하는 Filter와는 달리 Interceptor는 스프링 컨텍스트에서 동작합니다. 
  
</details>

-----------------------


