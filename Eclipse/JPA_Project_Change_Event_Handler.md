


### 첫번째 해결방안. 스프링 부트를 삭제한다.

[Help -> Eclipse MarketPlace -> Installed -> String Tools 4] 를 삭제한다.

 

### 두번째 해결방안. JPA 플러그인을 삭제한다.

1. [Help -> Eclipse MarketPlace -> Installed -> Eclipse Java EE Developer Tools 3.xx] 

2. Change 버튼 클릭

 - Dali Java Persistence Tools - EclipseLink JPA Support -> 해제

 - m2e-wtp - JPA Configurator for WTP (Optional) -> 해제

3. 두개의 플러그인을 삭제한 후 Problem을 확인하여, 오류 메세지가 발생하다면

다시 위의 두개의 플러그인을 다시 설치한다.

4. JPA Project Change Event Handler로 인한 프리징이 현상이 발견되지 않는것을 확인해 볼수 있다.

 

##### 스프링 부트를 꼭 써야 한다면 두번째 해결방안을, 스프링 부트가 필요 없다면 첫번째 해결방안을 사용하여

##### 필요에 따라 적용해보도록 한다.

### 그래도 계속 나올 시 
windows - properties - maven - java EE integration - JPA Configration, JAX-RS Conrigration, JSF Configration 체크 해제

