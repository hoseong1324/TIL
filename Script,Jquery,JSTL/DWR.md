#### Ajax- DWR 

##### 사용법

- dwr.jar 또는 dwr.war 파일 다운로드 후 톰캣설치폴더/lib 에 추가

- web.xml 코드 추가

  ```
  <servlet>
    <servlet-name>dwr-invoker</servlet-name>
    <display-name>DWR Servlet</display-name>
    <servlet-class>uk.ltd.getahead.dwr.DWRServlet</servlet-class>
    <init-param>
       <param-name>debug</param-name>
       <param-value>true</param-value>
    </init-param>
  </servlet>
  
  <servlet-mapping>
    <servlet-name>dwr-invoker</servlet-name>
    <url-pattern>/dwr/*</url-pattern>
  </servlet-mapping>
  ```

- web.xml 과 같은 위치에 dwr.xml 생성 후 코드 추가

```
<!DOCTYPE dwr PUBLIC
    "-//GetAhead Limited//DTD Direct Web Remoting 1.0//EN"
    "http://www.getahead.ltd.uk/dwr/dwr10.dtd">
<dwr>
  <allow>
    <create creator="new" javascript="JDate">
      <param name="class" value="java.util.Date"/>
    </create>
    <create creator="new" javascript="Demo">
      <param name="class" value="[패키지명.클래스]"/>
    </create>
  </allow>
</dwr>
```


- view 파일내에 코드 추가
```
  <script src='/[YOUR-WEBAPP]/dwr/interface/[YOUR-SCRIPT].js'></script>  
  <script src='/[YOUR-WEBAPP]/dwr/engine.js'></script>
  <script src='/[YOUR-WEBAPP]/dwr/util.js'></script>
```
