#### ajax
- 가장 흔히 쓰는 옵션
```
$.ajax({
    data: ,
    type: ,
    success: ,
    error : 
})
```

#### accepts (default: depends on dataType)           
Type : PlainObject                     
키/값 형태이며 해더에 포함한다. 어떤 종류의 응답을 받아들일지 서버에 알려주는 역할을 한다.           

#### async (default: true)   
Type : Boolean   
기본적으로 비동기 요청을 하도록 한다. 동기 요청이 필요하면 값을 false로 설정하면 된다.   

#### beforeSend   
Type: Function(  jqXHR jqXHR, PlainObject settings )   
전송 전에 실행되며 false 를 리턴하게 되면 요청이 취소된다.   

#### cache (default: true, false for dataType 'script' and 'jsonp')   
Type: Boolean   
false로 설정 시 브라우저에서 강제로 캐시되지 않도록 한다.   
false로 설정 시 HEAD 및 GET 요청 시 정상동작한다.   

#### complete   
Type: Function( jqXHR jqXHR, String textStatus )   
요청이 완료될 때 실행된다.   

#### contents   
Type: PlainObject   
Jquery가 내용을 고려하여 응답 구문을 분석하는 방법을 결정하는 옵션.   
새로운 데이터 유형을 정의할 때 사용된다.   

#### contentType (default: 'application/x-www-form-urlencoded; charset=UTF-8')   
Type: Boolean or String   
해더의 Content-Type을 설정한다.   

#### context   
Type: PlainObject   
특정 엘리먼트 또는 키/값 형태의 오브젝트를 context로 설정하여 callback 함수 등에서 사용할 수 있다.   

#### converters (default: {"* text": window.String, "text html": true, "text json": jQuery.parseJSON, "text xml": jQuery.parseXML})   
Type: PlainObject   
success 등의 콜백함수에 도착하기 전에 인터셉터한다.    
인터셉터 후 success 등의 콜백함수에서 데이터를 똑같이 사용하기 위해서는 데이터를 파싱해주어야 한다.    
(콜백 함수로 전달될 데이터를 반환)    
accepts 와 같이 사용할 수 있다. dataType이 자유로울 때 dataType별로 선행하는 작업이 사능하다.    

#### crossDomain (default: false for same-domain requests, true for cross-domain requests)    
Type: Boolean    
true로 설정할 경우 크로스 도메인 요청을 허용한다.    
   
#### data    
Type: PlainObject or String or Array   
서버로 보낼 데이터     

#### dataFilter      
Type: Function( String data, String type ) => Anything    
success 함수가 호출 되기 전에 실행된다.   
success로 전달할 데이터를 return 해야 한다.    

#### dataType (default: Intelligent Guess (xml, json, script, or html))    
Type: String    
서버에서 받을 데이터 형식을 지적한다.    
지정하지 않으면 MIME 타입을 참고하여 자동 파싱된다.   

#### error    
Type: Function( jqXHR jqXHR, String textStatus, String errorThrown )    
요청에 실패하면 호출된다.    

#### global (default: true)   
Type: Boolean    
global ajax 이벤트 핸들러를 사용할지 결정한다.   
false로 설정 시 ajaxStart, ajaxStop 등과 같은 이벤트로 제어할 수 없다.   

#### headers (default: {})   
Type: PlainObject     
해더 값을 키/값 형태로 설정(변경)할 수 있다.   

#### ifModified (default: false)    
Type: Boolean   
기본적으로 해더를 무시한다.    
true 설정 시 해더에서 Last-Modified 를 확인하며 응답이 변경된 경우(결과가 다른 경우)에만 요청을 처리한다.    

#### isLocal (default: depends on current location protocol)    
Type: Boolean    
jquery가 인식하지 않더라도 현재 환경을 local로 인식하도록 한다. isLocal 속성을 변경해야 할 경우에는 $.ajaxSetup() 함수를 사용한다.    

#### jsonp    
Type: String or Boolean   
콜백 함수명을 사용합니다. url에 포함된 쿼리 스트링 중 'callback=?' 문자열 중 'callback' 문자열을 대체 합니다.    
false로 설정 시 '?callback' 문자열이 url에 추가되는것을 방지하거나 '=?' 문자열의 변조를 방지할 수 있는데 이러한 경우엔 jsonpCallback을 활용해야 합니다.   

#### jsonpCallback    
Type: String or Function()   
jsonp 요청에 대한 callback 함수를 지정합니다.     

#### method (default: 'GET')     
Type: String    
요청할 HTTP 메서드이다. (POST, GET, PUT)    

#### mimeType    
Type: String   
MIME 타입을 설정한다.    

#### password    
Type: String    
HTTP 엑세스에 활용할 비밀번호를 설정한다.    

#### processData (default: true)    
Type: Boolean   
데이터를 querystring 형태로 보내지 않고 DOMDocument 또는 다른 형태로 보내고 싶으면 false로 설정한다.   


#### statusCode (default: {})    
Type: PlainObject    
HTTP 상태 코드별로 콜백함수를 호출 할 수 있다.   

#### success    
Type: Function( Anything data, String textStatus, jqXHR jqXHR )    
요청 성공 시 실행되는 콜백함수   

#### timeout     
Type: Number    
요청에 대해 밀리초 단위로 타임아웃을 설정할 수 있다.   

#### traditional      
Type: Boolean  
데이터에 배열을 전송할 때 데이터 직렬화를 하는 옵션이다.   

#### type (default: 'GET')    
Type: String    
get, post 중 전송방식을 선택한다.    

 

#### url (default: The current page)    
Type: String    
요청할 URL    

#### username    
Type: String    
HTTP 액세스 인증 요청에 응답하는데 사용할 사용자 이름.    

#### xhr (default: ActiveXObject when available (IE), the XMLHttpRequest otherwise)    
Type: Function()    
XMLHttpRequest 콜백 사용     

#### xhrFields    
Type: PlainObject    
xhr 객체에 fieldName-fieldValue 형태로 설정할 수 있다.    
예를들어 크로스도메인에서 withCredentials 값을 true로 설정할 수 있다.    

---

status code = 200         
statustext = parsererror                 

떴을 시 보낸 데이터 타입과 받는 데이터 타입이 달라서 발생하는 에러              
데이터타입을 맞춰주어야 한다.                 
