### Spring에서 지원하는 객체

- String test = test!=null ? test : 1 ;
```
public String test(httpServletRequest request){
  String test = ServletRequestUtils.getIntParameter(request,"test",1);
  String test = ServletRequestUtils.getStringParameter(request,"test","테스트");
}
```
#### ( request 변수, 가져올 파라미터 명, null 일시 Default 값 )
한글 인코딩에 문제가 있으므로 인코딩 해야함.

페이징처리 구문과 비교하면 조금 더 간결함.

현재 이해도는 이정도 더 추가할 예정이다.

