### JNDI 연동


```
<GlobalNamingResources>

<Resource auth="Container" 
description="User database that can be updated and saved" 
factory="org.apache.catalina.users.MemoryUserDatabaseFactory"
name="UserDatabase" 
pathname="conf/tomcat-users.xml" 
type="org.apache.catalina.UserDatabase"/>
```
***이곳에 접근 DB 내용 추가***

 <Resource name="JDNI이름" auth="Container"

​       driverClassName="oracle.jdbc.driver.OracleDriver"      
​       factory="org.apache.tomcat.jdbc.pool.BasicDataSourceFactory"    
​       type="javax.sql.DataSource"    
​       url="jdbc:oracle:thin:@서버아이피:포트:SID이름"    
​       username="사용자아이디"   
​       password="패스워드"    
        validationQuery="(Oracle)SELECT 1 FROM DUAL // (MySQL,MSSQL 등) SELECT 1 "    
       />



factory 부분은

​     "org.apache.tomcat.jdbc.pool.BasicDataSourceFactory"     

또는

​    "org.apache.tomcat.dbcp.dbcp.BasicDataSourceFactory"


```
 </GlobalNamingResources>
```
server.xml  에 context 부분에  추가
```
 <ResourceLink global="JNDI네임" name="JNDI네임" type="javax.sql.DataSource"/>
 ```
