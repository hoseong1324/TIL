### HAL 이란?
#### Hypertext Application Language 의 약자로 JSON, XML 코드 내의 외부 리소스에 대한 링크와 같은 하이퍼 미디어를 정의하기 위한 규칙      
 - 프로젝트 구성 방식에 대한 요구 사항을 부과 할 필요가 없기 때문에 여러 도메인에 쉽게 적용 가능            
  > HAL을 사용하는 모든 API에 쉽게 통합할 수 있는 범용 라이브러리를 만들 수 있음           
 #### 특성
 - 리소스와 링크라는 두 가지 개념을 기반으로 요소를 표현       

  > 리소스 : URI 링크, 임베디드 리소스, 표준 데이터, 비 URI 링크 등          

  > 링크 : 대상 URI, 링크 이름(rel), optional properties 등         

 - HAL이 갖는 미디어 타입                    
  > application/hal+json       
  > application/hal+xml       
  
#### 장점
 - API 자체에서 API 문서를 쉽게 찾을 수 있음(Self-Descriptive Message)   

 HAL 예시
```
{
	"_links" : {
    	"self" : {
        	"href" : "/api/exam"
        },
        "next" : {
        	"href" : "/api/exam/next"
        }
    },
    "id" : "hal-exam",
    "name" : "HAL 예시"
}
```

 - "_links"가 링크 정보를 갖는다.

 - "self", "next"는 링크의 이름(rel, relation)이다.
