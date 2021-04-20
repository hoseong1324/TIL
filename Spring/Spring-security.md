## Spring-Security 사용하기

### 1. pom.xml 추가
```
		  <!--스프링시큐리티 web 라이브러리-->                        
	    <dependency>
	        <groupId>org.springframework.security</groupId>
	        <artifactId>spring-security-web</artifactId>
	        <version>${org.springframework-version}</version>
	    </dependency>
	    <!--스프링시큐리티 core 라이브러리-->
	    <dependency>
	        <groupId>org.springframework.security</groupId>
	        <artifactId>spring-security-core</artifactId>
	        <version>${org.springframework-version}</version>
	    </dependency>
	    <!--스프링시큐리티 config 라이브러리-->
	    <dependency>
	        <groupId>org.springframework.security</groupId>
	        <artifactId>spring-security-config</artifactId>
	        <version>${org.springframework-version}</version>
	    </dependency>
```
### 2. root-context.xml 위치에 spring-security.xml 생성 

```
<?xml version="1.0" encoding="UTF-8"?> 

<beans:beans xmlns="http://www.springframework.org/schema/security"    

xmlns:beans="http://www.springframework.org/schema/beans"   

 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"   

 xsi:schemaLocation="http://www.springframework.org/schema/beans  

									    http://www.springframework.org/schema/beans/spring-beans.xsd 

 									   http://www.springframework.org/schema/security  

									    http://www.springframework.org/schema/security/spring-security.xsd">    

      <beans:bean id="bcryptPasswordEncoder" class="org.springframework.security.crypto.bcrypt.BCryptPasswordEncoder" /> </beans:beans>
```




### 3. web.xml 에 servlet 읽는 소스에 spring-security.xml 을 읽을 수 있게 param-value 추가해주기 


<?xml version="1.0" encoding="UTF-8"?>
<web-app version="2.5" xmlns="http://java.sun.com/xml/ns/javaee"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://java.sun.com/xml/ns/javaee https://java.sun.com/xml/ns/javaee/web-app_2_5.xsd">

	<!-- The definition of the Root Spring Container shared by all Servlets and Filters -->
	<context-param>
		<param-name>contextConfigLocation</param-name>
		<param-value>/WEB-INF/spring/root-context.xml</param-value>
		
	</context-param>
	
	<!-- Creates the Spring Container shared by all Servlets and Filters -->
	<listener>
		<listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
	</listener>

	<!-- Processes application requests -->
	<servlet>
		<servlet-name>appServlet</servlet-name>
		<servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
		<init-param>
			<param-name>contextConfigLocation</param-name>
			<param-value>/WEB-INF/spring/appServlet/servlet-context.xml</param-value>
			<param-value>/WEB-INF/spring/spring-security.xml</param-value>
			
		</init-param>
		<load-on-startup>1</load-on-startup>
	</servlet>
		
	<servlet-mapping>
		<servlet-name>appServlet</servlet-name>
		<url-pattern>/</url-pattern>
	</servlet-mapping>

</web-app>




### 4. Class 또는 Method 내에서  PasswordEncoder Inject 또는 autowired 해주고 암호화시키기

   ( VO에 넣은 다음 회원가입을 진행하는 방식 )

   
```
   public String security(String pw){

   	@Inject // @Autowired

   	BCryptPasswordEncoder passwordEncoder;
  
   	String Spw = passwordEncoder.encode(pw);
   	vo.setPw(Spw);
}
```
 

### 5. 로그인할때 비교를 위해 match 시켜보기 < 매치를 위해 service를 먼저 호출하여 데이터를 가져온 후 매칭 >

   
  ```
   VO login = service.login(vo); 

   boolean pwMatch = pwdEncoder.matches(vo.getPw(), login.getPw());
```


 ##### 이후 조건을 걸어 로그인 처리
