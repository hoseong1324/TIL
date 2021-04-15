```
@Controller
	- 컨트롤러 설정

@RestController
	- Spring에서 Controller 중 View로 응답하지 않는, 컨트롤러를 의미

@Service
	- 서비스 설정

@Interface
	- 인터페이스 설정

@Repository
	- DAO class 에서 쓰인다. 데이터베이스에 접근하는 메서드를 가지고 있는 클래스에서 쓰임

@Autowired
	- 속성(field), setter method, constructor(생성자)에서 사용한다. 무조건적인 객체에 대한 의존성을 주입

@Resource
- @Autowired와 마찬가지로 빈 객체를 주입해주는데 차이점은 Autowired는 타입으로, Resource는 이름으로 연결해준다

@Inject
	- Autowired 어노테이션과 비슷한 역할을 한다.
	-  Autowired는 스프링 에서만 쓰이는 어노테이션

@Alias("") 
	- DTO, VO 에 매퍼 ResultType  네임스페이스 설정

@RequestMapping("url") or @RequestMapping(value="url", method=(RequestMethod.POST/GET)
	- Spring의 컨트롤러 혹은 그 메서드의 URI를 정의
	- GET, POST, PATCH, PUT, DELETE 를 정의
	- 요청 받는 형식을 정의하지 않는다면, 자동적으로 GET

@RequestParam(required = false or true ) 자료형 변수
	- 파라미터 값 가져오기
	- GET 에서 넘긴 파라미터를 메서드의 인자로 매칭하는 식으로 사용

@RequestBody
	- POST나 PUT, PATCH로 요청을 받을때에, 요청에서 넘어온 body 값들을 자바 타입으로 파싱

@ResponseBody
	- HttpMessageConverter 를 이용하여 JSON 혹은 xml 로 요청에 응답할수 있게 해주는 어노테이션

@Required
	- Required 어노테이션을 사용하여 optional 하지 않은, 꼭 필요한 속성들을 정의한다

@PathVariable
	- URI에서 / 다음으로 넘어오는 값들을 파싱하는 어노테이션
	POST /index/{idx}와 같이 uri가 전달될 때 해당하는 구분자 {idx}를 받아온다
	
	
@ResponseStatus
	-  사용자에게 원하는 response code와 reason을 리턴해주는 애노테이션

@ExceptionHandler(ExceptionClassName.class)
	- 해당 클래스의 예외를 캐치하여 처리한다.

@PathVariable
	- 메서드 파라미터 앞에 사용하면서 해당 URL에서 {특정값}을 변수로 받아 올 수 있다.

@RequestAttribute
	- Request에 설정되어 있는 속성 값을 가져올 수 있다
	
@SessionAttributes
	-  세션에 데이터를 넣을 때 쓰는 애노테이션
	
@ModelAttribute
	- view에서 전달해주는 파라미터를 클래스(VO/DTO)의 멤버 변수로 binding 해주는 애노테이션
```
https://gmlwjd9405.github.io/2018/12/02/spring-annotation-types.html


