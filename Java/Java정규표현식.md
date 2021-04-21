*정규 표현식*


#### 자주 쓰이는 정규 표현식

* 숫자 : ^[0-9]*$	
* 영문자 : ^[a-zA-Z]*$
* 영어 & 숫자^[a-zA-Z0-9]*$
* 한글 : ^[가-힣]*$
* E-Mail : \\w+@\\w+\\.\\w+(\\.\\w+)?
* 전화번호 :  ^\d{2,3}-\d{3,4}-\d{4}$
* 휴대전화번호 : ^01(?:0|1|[6-9])-(?:\d{3}|\d{4})-\d{4}$
* 주민등록번호 : \d{6} \- [1-4]\d{6}
* 우편번호 : ^\d{3}-\d{2}$
* * *

![image](https://user-images.githubusercontent.com/59944238/114512886-89fb0180-9c74-11eb-8d6d-a1b1f6f3b562.png)

* * *
```
import java.util.regex.Pattern;

public class RegexExample {
	public static void main(String[] args)  {
    
            String pattern = "^[0-9]*$"; //숫자만
            String val = "123456789"; //대상문자열
        
            boolean regex = Pattern.matches(pattern, val);
            System.out.println(regex);
    }
}
```
* Pattern 클래스 주요 메서드
* compile(String regex) : 주어진 정규표현식으로부터 패턴을 만듭니다.
* matcher(CharSequence input) : 대상 문자열이 패턴과 일치할 경우 true를 반환합니다.
* asPredicate() : 문자열을 일치시키는 데 사용할 수있는 술어를 작성합니다.
*  pattern() : 컴파일된 정규표현식을 String 형태로 반환합니다.
* split(CharSequence input) : 문자열을 주어진 인자값 CharSequence 패턴에 따라 분리합니다.

* Parttern 플래그 값 사용(상수)
*  Pattern.CANON_EQ : None표준화된 매칭 모드를 활성화합니다.
* Pattern.CASE_INSENSITIVE : 대소문자를 구분하지 않습니다. 
* Pattern.COMMENTS : 공백과 #으로 시작하는 주석이 무시됩니다. (라인의 끝까지).
* Pattern.MULTILINE : 수식 ‘^’ 는 라인의 시작과, ‘$’ 는 라인의 끝과 match 됩니다.
* Pattern.DOTALL : 수식 ‘.’과 모든 문자와 match 되고 ‘\n’ 도 match 에 포함됩니다.
* Pattern.UNICODE_CASE : 유니코드를 기준으로 대소문자 구분 없이 match 시킵니다.
* Pattert.UNIX_LINES : 수식 ‘.’ 과 ‘^’ 및 ‘$’의 match시에 한 라인의 끝을 의미하는 ‘\n’만 인식됩니다.
* * *

```
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class RegexExample {
	public static void main(String[] args)  {
            Pattern pattern = Pattern.compile("^[a-zA-Z]*$"); //영문자만
            String val = "abcdef"; //대상문자열
	
            Matcher matcher = pattern.matcher(val);
            System.out.println(matcher.find());
	}
}
```

* Matcher 클래스 주요 메서드
* matches() : 대상 문자열과 패턴이 일치할 경우 true 반환합니다.
* find() : 대상 문자열과 패턴이 일치하는 경우 true를 반환하고, 그 위치로 이동합니다.
* find(int start) : start위치 이후부터 매칭검색을 수행합니다.
* start() : 매칭되는 문자열 시작위치 반환합니다.
* start(int group) : 지정된 그룹이 매칭되는 시작위치 반환합니다.
* end() : 매칭되는  문자열 끝 다음 문자위치 반환합니다.
* end(int group) : 지정되 그룹이 매칭되는 끝 다음 문자위치 반환합니다.
* group() : 매칭된 부분을 반환합니다.
* group(int group) : 매칭된 부분중 group번 그룹핑 매칭부분 반환합니다. 
* groupCount() : 패턴내 그룹핑한(괄호지정) 전체 갯수를 반환합니다

