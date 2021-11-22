#### REST 를 보다 RESTful하게 만들자

https://pronist.tistory.com/146

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
