### 기본 인/디코딩

- import java.net.URLEncoder;
- import java.net.URLDecoder;

```
String url = "test";
// URLEncoder.encode(변수, "형식")
String e_url = URLEncoder.encode(url,"UTF-8);

// URLDecoder.decode(변수, "형식") 
Strung D_url = URLDecoder.decode(e_url,"UTF-8");
```

▣ URLEncoder 변환규칙 
- 아스키문자(a-z, A-Z, 1-9),  '.',  '-',  '*',  '_' : 그대로 전달 
- 공백문자(' ') : '+' 기호로 변환됨 
- 기타문자 : '%xy' 와 같이 세 개의 문자로 변환되며, 이 때 xy는 해당 문자의 ASCII코드를 16진수화한 결과를 두자리의 대문자로 나타낸 것이다.
- URLEncoder를 이용한 웹인코딩 
- String enStr = URLEncoder.encode("네이버-www.naver.com", "EUC_KR");

▣ URLDecoder를 이용한 웹디코딩 
- String enStr = URLEncoder.encode("네이버-www.naver.com", "EUC_KR"); 
- String deStr = URLDecoder.decode(enStr, "EUC_KR"); 



### BASE64를 직역하면 64진법이라는 말 
* 8bit 이진 데이터를 문자코드에 영향 받지않게 공통 ASCII 영역의 문자로 이루어진 일련의 문자열로 바꾸는 인코딩 방식

* 62개까지는 A-Z(대문자), a-z(소문자), 0-9(숫자) 로 되어있고 마지막 두개의 기호를 어떤 것을 쓰냐에 따라 여러가지의 변종이 생김

* 순서 - 원본 문자열> ASCII binary> 6bit로 cut> base64 encodeing

* BASE64 를 사용하는 이유
- 제어문자와 특수문자를 제외한 64개의 안전한 문자만을 사용하기 때문이다.
- (안전한 출력 문자란 문자 코드에 영향을 받지 않는 공통 ASCII를 의미)

* * *

- import sun.misc.BASE64Encoder;
- import sun.misc.BASE64Decoder;
```
BASE64Encoder encoder = new BASE64Encoder();
System.out.println(encoder.encode(test));
BASE64Decoder decoder = new BASE64Decoder();
System.out.println(decoder.decode(test));
```

### BASE64Encoder, BASE64Decoder 임포트가 되지 않을 시
* import sun.misc.BASE64Encoder;
* import sun.misc.BASE64Decoder;


#### 해결방안 1
- import org.apache.commons.codec.binary.Base64;
```
byte[] encodedBytes = Base64.encodeBase64("Test".getBytes());
System.out.println("encodedBytes " + new String(encodedBytes));
byte[] decodedBytes = Base64.decodeBase64(encodedBytes);
System.out.println("decodedBytes " + new String(decodedBytes));
```


#### 해결방안 2
- import java.util.Base64;
```
byte[] encodedBytes = Base64.getEncoder().encode("Test".getBytes());
System.out.println("encodedBytes " + new String(encodedBytes));
byte[] decodedBytes = Base64.getDecoder().decode(encodedBytes);
System.out.println("decodedBytes " + new String(decodedBytes));
```
