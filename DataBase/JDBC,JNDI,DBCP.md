#### JDBC ( Java DataBase Connectivity )

- 데이터베이스 풀( DB Pool ) 방식을 사용하지 않고 DB에서 정보를 가져올 때마다 계속해서 DB를 열고 닫는 방식
  - 객체 생성, 커넥션 연결, 커넥션종료 등을 반복하기때문에 효율성이 매우 떨어짐
  - 위와 같은 이유로 상용화된 어플리케이션에서는 JDBD 방식을 거의 사용하지 않는다

#### JNDI ( Java Naming and Directory Interface)

- WAS 단에 데이터베이스 커넥션 객체를 미리 네이밍 해놓는 방식
  - DB 커넥션을 WAS ( Web Application Server ) 단에서 제어하며 서버에서 하나의 커넥션 풀을 가짐.
  - DB 설정 정보 파악 쉬움, 커넥션 풀 효율적인 사용 가능

#### DBCP ( DataBase Connetion Pool )

- DBCP 를 Application 소스에 설정해놓은 방식
  - 기본적인 원리 - 어플리케이션을 시작할 때 원하는 만큼 커넥션 객체를 만들어놓고 pool에 넣어놓았다가 필요할 때마다 가져다 쓰고 다시 pool에 반납하는 방식
  - DBCP 를 Application 소스에 설정해놓은 방식
