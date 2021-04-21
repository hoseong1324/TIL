### JNDI 연동

### 현재 정확하지 않음 수정 예정

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
```
 <Resource name="JNDI이름" auth="Container"

​       driverClassName="oracle.jdbc.driver.OracleDriver"      
​       factory="org.apache.tomcat.jdbc.pool.BasicDataSourceFactory"    
​       type="javax.sql.DataSource"    
​       url="jdbc:oracle:thin:@서버아이피:포트:SID이름"    
​       username="사용자아이디"   
​       password="패스워드"    
​       validationQuery="(Oracle)SELECT 1 FROM DUAL // (MySQL,MSSQL 등) SELECT 1 "    
       />
```


factory 부분은

​    ` "org.apache.tomcat.jdbc.pool.BasicDataSourceFactory"     `   
또는     
​  `  "org.apache.tomcat.dbcp.dbcp.BasicDataSourceFactory"     `


```
 </GlobalNamingResources>
```
server.xml  에 context 부분에  추가
```
 <ResourceLink global="JNDI네임" name="JNDI네임" type="javax.sql.DataSource"/>
 ```
 
 
 
 
 #### Resource 부분 정리
 Resource

- name : JNDI 이름. Context의 lookup()을 사용하여 자원을 찾을 때 사용.

- auth : resource manager 에 sign on 하는 주체로 Container (container-managed 일 경우) 혹은 Application (application-managed 일 경우)

- type : Resource의 형태를 지정. (패키지 이름 포함한 클래스 이름)

- driverClassName : JDBC 드라이버 클래스 지정 (패키지 이름 포함)

- url : DB connection URL

- username : DB접속 계정

- password : DB접속 암호

- maxActive : DataSource로 부터 꺼낼 수 있는 connection 최대 수. (기본값 8)

- maxIdle : DataSource에서 Connection pool 유지될 수 있는 사용하지 않는(대기) connection 최대 개수. 최대 개수 초과 시 반납되는 connection은 닫힘. (기본갑 8)

- maxWait : 발급한 connection 개수가 최대값에 도달한 상태에서 다시 connection을 요청할 경우 준비하기 위한 최대 대기시간(milliseconds). 최대 대기시간이 지나도 반납되는 connection이 없으면 예외를 던진다. (기본값 -1, 커넥션 반납 무한대기)

- minIdle : maxActive 를 넘을 수 없으므로 때에 따라 idle connection 이 minIdle 보다 적을 수도 있고, -1 일 경우 무제한이며, default 는 0

- testWhileIdle : idle connection 대상으로 validationQuery를 수행하여 문제가 발생할 경우 pool 에서 제거한다. 그리고 그 주기는 timeBetweenEvictionRunsMillis인데 물론 validationQuery 가 우선한다.

- validationQuery : connection 유효성 체크 query 로 default 는 null 이다. 만일 MySQL/MariaDB/PPAS/PostgreSQL 에 적용하려면 select 1, Oracle 에 적용하려면 select 1 from dual 을 사용한다.

- closeMethod : Tomcat Server가 종료될 때, 자원 해제를 위해서 호출하는 메서드. (매개변수는 없어야 함.)
 
