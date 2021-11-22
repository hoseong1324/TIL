### REST 제약조건

- 1.Client -server      
// 서버와 클라이언트를 가져야 한다.     
- 2.Stateless         
// 상태를 가지면 안된다.  
 ##### Stateless - client와 server의 동작, 상태정보를 저장하지 않는 형태
- 3.Cacheable                
// 요청에 대한 응답 내의 데이터에 해당 요청은 캐시가 가능한지 불가능 한지 명시해야 한다.            
// 보통 HTTP Header에 cache-control 헤더를 이용한다.
- 4.Layerd system        
// 레이어드 시스템 이어야 한다.     
API 서버는 순수 비지니스 로직을 수행 한다.     
클라이언트는 대상 서버에 직접 연결되었는지, 또는 중간 서버를 통해 연결되었는지 인지 할 수 없다.        
- 5.code-on-demand (optional)(주문형 코드)               
// 서버에서 코드를 클라이언트에게보내서 실행 가능해야한다. (js)    
//  code on demand라는 것은 client에 보내는 데이터를 바로 실행 가능한 코드를 보내서 이것을 Client에서 실행하는 것
##### 위의 조건들은 HTTP 통신을 이용하면 자동으로 만족한다.               
- 6.uniform interface(균일한 인터페이스)               
// HTTP 통신을 하면 만족하는 것                 
##### identifcation of resources(자원 식별)   
// 자원으로 식별 할 수 있어야한다.
//URI 를 통한 식별
##### manipulation of resources through representations(표현을 통한 자원 조작)    
표현을 통해 자원을 조작 할 수 있어야 한다.     
HTTP 메소드를 통해 자원 조작 (CRUD 가능)    
만족하지 않는 것 추가 구현을 통해 만족 시켜야 한다.     
##### self-descriptive messages(자기 설명적 메시지) 
메시지가 스스로를 설명 해야한다.     
목적지가 있아여 한다.      
##### hypermedia as the engine of application state (HATEOAS) //[HATEOAS란?](https://github.com/hoseong1324/TIL/blob/main/API/HATEOAS.md)          
##### (애플리케이션 상태의 엔진으로서의 하이퍼미디어)     
애플리케이션의 상태가 Hyperlink 를 통해서 전송되어야한다.다음 상태를 링크로 표시해야한다.


하지만 Uniform Interface 은 만족하는 것도 있고 만족 하지 않는 것도 있다.                      

---   


### REST 를 보다 RESTful하게 만들자


### RESTful 하게 API 만들기

- 마지막이 / 로 끝나지 않는다.    
/// [x]	http://api.test.com/users/     
/// [o] http://api.test.com/users      
- _ ( 언더바 ) 보단 - 를 사용한다    
/// [x] http://api.test.com/tag/rest_api     
/// [o] http://api.test.com/tag/rest-api    
- 대문자대신 소문자를 사용한다.    
/// [x] http://api.test.com/tag/REST-API
/// [o] http://api.test.com/tag/rest-api  
- 동사는 포함하지 않고 메소드로 대체한다.    
/// [x] POST http://api.test.com/delete-user/1   
    [x] POST http://api.test.com/delete/user/1	   
/// [o] DELETE http://api.test.com/user/1    
- 이미지 파일 관련시 파일 확장자를 포함하지 않는다.   
/// [x] http://api.test.com/users/1/profile.png   
/// [o] http://api.test.com/users/1/profile (Accept 사용)    
Accept: image/png   
