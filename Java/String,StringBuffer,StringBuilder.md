### String
* String은 불변성을 가지므로 String 객체의 문자열을 수정하면 새로운 객체의 String이 생성되는 것이다.

### StringBuffer/ StringBuilder
* String 과 다르게 가변성을 가지므로 한 객체에서 수정이 가능하다.

### StringBuffer/ StringBuilder 차이
- 가장 큰 차이점은 동기화의 유무이다
- StringBuffer는 동기화 키워드를 지원해서 멀티쓰레드 환경에서 안전함에 비해 StringBulider는 동기화를 지원하지 않기때문에 멀티쓰레드 환경에서는 적합하지 않다.
- 반대로 생각하면 단일쓰레드 환경에서는 StringBuilder가 StringBuffer보다 성능이 더 뛰어나다

### 정리
```
String          :  문자열 연산이 적고 멀티쓰레드 환경일 경우
StringBuffer    :  문자열 연산이 많고 멀티쓰레드 환경일 경우
StringBuilder   :  문자열 연산이 많고 단일쓰레드이거나 동기화를 고려하지 않아도 되는 경우
```

