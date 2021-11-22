### API 란 ? 
Application Programming Interface 의 약자로 애플리케이션 소프트웨어를 구축하고 통합하는 정의 및 프로토콜 세트다.      
예를 들어 사용자와 생산자가 있을 때, 사용자에게는 사용자가 원하는 값을, 생산자에게는 생산자가 원하는 값을 전달하는 중간매개체같은 역할.       
즉, API를 사용자 또는 클라이언트, 그리고 사용자와 클라이언트가 얻으려 하는 리소스 사이의 조정자로 생각하면 됩니다.      

### Spring API Swagger 문서 자동화 하기
- Maven Project
#### 1.pom.xml 추가
```
<!-- https://mvnrepository.com/artifact/io.springfox/springfox-swagger2 -->
<dependency>
    <groupId>io.springfox</groupId>
    <artifactId>springfox-swagger2</artifactId>
    <version>2.9.2</version>
</dependency>

<!-- https://mvnrepository.com/artifact/io.springfox/springfox-swagger-ui -->
<dependency>
    <groupId>io.springfox</groupId>
    <artifactId>springfox-swagger-ui</artifactId>
    <version>2.9.2</version>
</dependency>
```
- Gradle Project
```
// https://mvnrepository.com/artifact/io.springfox/springfox-swagger2
compile group: 'io.springfox', name: 'springfox-swagger2', version: '2.9.2'

// https://mvnrepository.com/artifact/io.springfox/springfox-swagger-ui
compile group: 'io.springfox', name: 'springfox-swagger-ui', version: '2.9.2'
```
#### 2. swaggerConfig.java 파일 생성
```
@Configuration
@EnableSwagger2
public class SwaggerConfig {
	
	@Bean
	public Docket api() {
		return new Docket(DocumentationType.SWAGGER_2)
				.select()
				.apis(RequestHandlerSelectors.any())
				.paths(PathSelectors.any())
				.build();
	}
}
```
- 여기까지 하고 실행 후 http://localhost:8080/swagger-ui.html/ 로 접속해보면 API 문서가 생성된 것을 확인할 수 있다 

#### Annotation
- ApiOperation
@ApiOperation으로 해당 Controller 안의 method의 설명을 추가할 수 있다.     
   ` @ApiOperation(value = "Swagger-API-Test", notes = "Swagger-API 를 테스트한다.")     `
- ApiImplicitParam
@ApiImplicitParam = Request Parameter 설명     
@ApiImplicitParam Annotation으로 해당 API Method 호출에 필요한 Parameter들의 설명을 추가할 수 있다.    
 ```
 @ApiImplicitParam(        name = "id"
         , value = "사용자 아이디"
        , required = true
        , dataType = "string"
        , paramType = "path"
        , defaultValue = "None")
```
        dataType, paramType, required의 경우 해당 name의 정보가 자동으로 채워지므로 생략 할 수 있다.

paramType의 경우     
@RequestParam은 query를,     
@PathVariable은 path를 명시해주면 된다.     
만약 해당 Method의 Parameter가 복수일 경우,      
@ApiImplictParams로 @ApiImplictParam을 복수개 사용할 수 있다.

### 3. @ApiResponses Annotation으로 응답에 대한 설명 추가
```
@ApiResponses({
	@ApiResponse(code = 200, message = "로그인 성공"),
	@ApiResponse(code = 400, message = "잘못된 접근"),
	@ApiResponse(code = 500, message = "서버 에러")
})
```
해당 메소드에서 사용하지 않지만 디폴트로 나오는 응답 코드들을 삭제하려면 SwaggerConfig.java 파일에 한 줄만 추가하면 된다.
```
@Configuration
@EnableSwagger2
public class SwaggerConfig {

    @Bean
    public Docket api() {
        return new Docket(DocumentationType.SWAGGER_2)
                .useDefaultResponseMessages(false)	//추가
                .select()
                .apis(RequestHandlerSelectors.any())
                .paths(PathSelectors.any())
                .build();
    }
}
```
### 4.@ApiModelProperty Annotation으로 해당 파라미터에 대한 example 값 추가
```
@Data
public class LoginReq {
    @ApiModelProperty(example = "신혜란")
    private String name;
    @ApiModelProperty(example = "hyeran")
    private String password;
}
```
### 5.Swagger UI 페이지에 보여지는 API 정보 커스텀하기

SwaggerConfig.java 파일에 ApiInfo 메서드 추가
```
@SuppressWarnings("deprecation")
private ApiInfo apiInfo() {
	ApiInfo apiInfo = new ApiInfo(
            "Title",
            "Description",
            "Version",
            "Terms of Service URL",
            "contact Name",
            "License",
            "License URL"
    );
    return apiInfo;
 }
@Bean
public Docket api() {
	return new Docket(DocumentationType.SWAGGER_2)
			.useDefaultResponseMessages(false)
			.apiInfo(apiInfo()) //추가
			.select()
			.apis(RequestHandlerSelectors.any())
			.paths(PathSelectors.any())
			.build();
}
```
