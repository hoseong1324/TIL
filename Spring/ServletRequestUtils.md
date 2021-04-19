### Spring에서 지원하는 객체

- String test = test!=null ? test : 1 ;


- String test = ServletRequestUtils.getIntParameter(test,"test",1);
- String test = ServletRequestUtils.getStringParameter(test,"test","테스트");

test 가 null 이면 "test" 를 null 이 아니면 3번째 파라미터값을 넘긴다 (생략가능)

한글 인코딩에 문제가 있으므로 인코딩 해야함.

페이징처리 구문과 비교하면 조금 더 간결함.

현재 이해도는 이정도 더 추가할 예정이다.

