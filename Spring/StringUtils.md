
## StringUtils  찾아서 쓰기 위한 복붙 ( 이해보다 빠른 검색을 위함 )

**라이브러리 직접다운 url**
https://commons.apache.org/proper/commons-lang/download_lang.cgi

**Maven사용 pom.xml 사용**
```

<!-- https://mvnrepository.com/artifact/org.apache.commons/commons-lang3 -->

<dependency>

  <groupId>org.apache.commons</groupId>

  <artifactId>commons-lang3</artifactId>

  <version>3.8</version>

</dependency>
```

**StringUtils.abbreviate(문자열, 보여줄숫자(...포함))** 

문자열 축소하기 뒤에 숫자는 4보다 커야한다.

긴글을 정해진 글자만큼만 보여주고 ... 으로 요약한다고 생각하면된다.

> String abbreviate = StringUtils.abbreviate("ShowMeTheMoney", 7);
>
> System.out.println(abbreviate);
>
> //출력결과 : Show...

​		

**StringUtils.appendIfMissing(문자열, 추가할단어, 마지막단어)**

마지막단어가 다를 경우 추가할단어를 추가해준다(대소문자를 구분한다),

> String appendIfMissing = StringUtils.appendIfMissing("ShowMeTheMoney", "-From.Choi", "Money");
>
> System.out.println(appendIfMissing);
>
> //출력결과 : ShowMeTheMoney
>
> ​		
>
> appendIfMissing = StringUtils.appendIfMissing("ShowMeTheMoney", "-From.Choi", "test");
>
> System.out.println(appendIfMissing);
>
> //출력결과 : ShowMeTheMoney-From.Choi

​		

**StringUtils.appendIfMissingIgnoreCase(문자열, "추가할단어", "마지막단어")**

StringUtils.appendIfMissing와 같으나 대소문자를 구분하지않는다.

> String appendIfMissingIgnoreCase = StringUtils.appendIfMissingIgnoreCase("ShowMeTheMoney", "-From.Choi", "money");
>
> System.out.println(appendIfMissingIgnoreCase);
>
> //출력결과 : ShowMeTheMoney

​		

**StringUtils.capitalize(문자열)**

첫글자를 대문자로 변환한다.

> String capitalize = StringUtils.capitalize("sss");
>
> System.out.println(capitalize);
>
> 출력결과 : Sss

​		

**StringUtils.chomp(문자열);**

마지막에 개행문자 \n,\r,\r\n이 있을 경우 제거한다.

> String chomp = StringUtils.chomp("ssssss\n");
>
> System.out.println(chomp);
>
> //출력결과 : ssssss

​		

**StringUtils.chomp(문자열,제거할문자);**

마지막에 제거할 문자가 있을 경우 제거한다.

> String chomp2 = StringUtils.chomp("ssssss#","#");
>
> System.out.println(chomp2);
>
> //출력결과 : ssssss

​		

**StringUtils.chop(문자열)**

마지막 문자 하나를 제거한다.

> ​		String chop = StringUtils.chop("ssssss");
>
> ​		System.out.println(chop);
>
> ​		//출력결과 : sssss

​		

**StringUtils.center(문자열, 글자수);**

문자열에 설정한 글자수만큼 공백을 추가한다.

오른쪽,왼쪽 순으로 추가된다.

> ​		String center = StringUtils.center("sss", 12);
>
> ​		System.out.println(center);
>
> ​		//출력결과 :   sss   

​		

**StringUtils.center(문자열, 글자수, 추가될단어);**

문자열에 설정한 글자수만큼 추가될 단어를 추가한다.

오른쪽,왼쪽 순으로 추가된다.

> ​		String center2 = StringUtils.center("sss", 12, "#");
>
> ​		System.out.println(center2);
>
> ​		//출력결과 : ####sss#####

​		

​		

**StringUtils.compare(문자열, 비교할문자열)**

문자열을 십진수로 변환후 비교한다.

문자를 유니코드 코드 (10진수) 로 변환 출력

> ​		System.out.println((int) '가');
>
> ​		System.out.println((int) '나');
>
> ​		//출력결과 : 44032
>
> ​		//출력결과 : 45208
>
> ​		int compare = StringUtils.compare("가", "나");
>
> ​		System.out.println(compare);
>
> ​		//출력결과 : -1176
>
> ​		//사용할 일이 있을려나...

​		

**StringUtils.compareIgnoreCase(문자열, 비교할문자열)**

문자열을 십진수로 변환후 비교한다.(대소문자를 비교안함)

> ​		int compareIgnoreCase = StringUtils.compareIgnoreCase("S", "s");
>
> ​		System.out.println(compareIgnoreCase);
>
> ​		//출력결과 : 0

​		

**StringUtils.contains(문자열, 비교할문자열)**

문자열안에 비교할문자열이 포함되어있으면 true를 반환한다.

> ​		boolean contains = StringUtils.contains("ssss", "ss");
>
> ​		System.out.println(contains);
>
> ​		//출력결과 : true

​		

**StringUtils.containsAny(문자열, 비교할문자열, 비교할문자열)**

문자열안에 비교할문자열이 하나라도 포함되어있으면 true를 반환한다.

> ​		boolean containsAny = StringUtils.containsAny("안녕하세요", "동안");
>
> ​		System.out.println(containsAny);
>
> ​		//출력결과 : true

​		

**StringUtils.containsIgnoreCase(문자열, 비교할문자열)**

문자열안에 비교할문자열이 포함되어있으면 true를 반환한다.(대소문자를 비교안함)

> ​		boolean containsIgnoreCase = StringUtils.containsIgnoreCase("ss", "SS");
>
> ​		System.out.println(containsIgnoreCase);
>
> ​		//출력결과 : true

​		

**StringUtils.containsNone(문자열, 비교할문자열)**

문자열안에 비교할문자열이 하나라도 포함되어있으면 false를 반환한다.

> ​		boolean containsNone = StringUtils.containsNone("ssa", "axx");
>
> ​		System.out.println(containsNone);
>
> ​		//출력결과 : false







**StringUtils.containsOnly(문자열, 비교할문자열)**

문자열안에 비교할문자열이 모두 포함되어있으면 true를 반환한다.

> ​		boolean containsOnly = StringUtils.containsOnly("ssa", "asd");
>
> ​		System.out.println(containsOnly);
>
> ​		//출력결과 : true

​		

**StringUtils.containsWhitespace(문자열, 비교할문자열)**

문자열안에 공백이 포함되어 있으면 true를 반환한다.

> ​		boolean containsWhitespace = StringUtils.containsWhitespace("sss sss sss");
>
> ​		System.out.println(containsWhitespace);
>
> ​		//출력결과 : true

​		

**StringUtils.countMatches(문자열, 비교할문자열)**

문자열안에 비교할 문자열이 있으면 출력결과에 1씩 추가한다.

> ​		int countMatches = StringUtils.countMatches("ccaaaa", "cc");
>
> ​		System.out.println(countMatches);
>
> ​		//출력결과 : 1

​		

**StringUtils.defaultIfBlank(문자열, 반환할문자열)**

문자열이 띄어쓰기,공백이,null인 경우 반환할 문자열을 반환한다.

> ​		String defaultIfBlank = StringUtils.defaultIfBlank(" ", "띄어쓰기,공백이,null일시 반환문자");
>
> ​		System.out.println(defaultIfBlank);
>
> ​		//출력결과 : 공백일시 반환문자

​		

**StringUtils.defaultIfEmpty(문자열, 반환할문자열)**

문자열이 공백,null인 경우 반환할 문자열을 반환한다.

> ​		String defaultIfEmpty = StringUtils.defaultIfEmpty("", "공백,null일시 반환문자");
>
> ​		System.out.println(defaultIfEmpty);
>
> ​		//출력결과 : 공백일시 반환문자

​		

**StringUtils.defaultString(문자열, 반환할문자열)**

문자열이 null인 경우 반환할 문자열을 반환한다.(반환할문자열이 없을경우 ""로 반환한다.)

> ​		String defaultString = StringUtils.defaultString(null,"null일시 반환문자");
>
> ​		System.out.println(defaultString);
>
> ​		//출력결과 : null일시 반환문자

​		

**StringUtils.deleteWhitespace(문자열)**

문자열에 공백이 있을경우 제거한다.

> ​		String deleteWhitespace = StringUtils.deleteWhitespace("안녕 하세요");
>
> ​		System.out.println(deleteWhitespace);
>
> ​		//출력결과 : 안녕하세요



**StringUtils.difference(문자열,비교할문자열)**

문자열과 비교할문자열을 비교하고 비교할문자열에서 다른부분을 반환한다.

> ​		String difference = StringUtils.difference("안녕하시오", "안녕하세오");
>
> ​		System.out.println(difference);
>
> ​		//출력결과 : 세요



**StringUtils.endsWith(문자열,마지막문자열)**

문자열의 마지막이 마지막문자열과 비교하고 같다면 true을 반환한다.

> ​		boolean endsWith = StringUtils.endsWith("안녕하세요.", ".");
>
> ​		System.out.println(endsWith);
>
> ​		//출력결과 : true

​		

**StringUtils.endsWithAny(문자열,마지막문자열)**

문자열의 마지막이 마지막문자열과 비교하고 같다면(vararg형식) true을 반환한다.(대/소문자를 구분한다)

> ​		boolean endsWithAny = StringUtils.endsWithAny("안녕하세요.s", ".S");
>
> ​		System.out.println(endsWithAny);
>
> ​		//출력결과 : false

​	

**StringUtils.endsWithAny(문자열,마지막문자열)**

문자열의 마지막이 마지막문자열과 비교하고 같다면 true을 반환한다.(대/소문자를 구분안한다)

> ​		boolean endsWithIgnoreCase = StringUtils.endsWithIgnoreCase("안녕하세요.s", ".S");
>
> ​		System.out.println(endsWithIgnoreCase);
>
> ​		//출력결과 : true

​		

**StringUtils.equals(문자열,비교할문자열)**

문자열과 비교할문자열과 같다면 true을 반환한다.

> ​		boolean equals = StringUtils.equals("비교", "비교");
>
> ​		System.out.println(equals);
>
> ​		//출력결과 : true



**StringUtils.equalsAny(문자열,비교할문자열)**

문자열과 비교할문자열과 같다면(vararg형식) true을 반환한다.

> ​		boolean equalsAny = StringUtils.equalsAny("ss", "sS","ss");
>
> ​		System.out.println(equalsAny);
>
> ​		//출력결과 : false

​		

**StringUtils.equalsAnyIgnoreCase(문자열,비교할문자열)**

문자열과 비교할문자열과 같다면(vararg형식) true을 반환한다.(대/소문자를 구분안한다)

> ​		boolean equalsAnyIgnoreCase = StringUtils.equalsAnyIgnoreCase("ss", "sS","ss");
>
> ​		System.out.println(equalsAnyIgnoreCase);
>
> ​		//출력결과 : ture

​		

**StringUtils.equalsIgnoreCase(문자열,비교할문자열)**

문자열과 비교할문자열과 같다면 true을 반환한다.(대/소문자를 구분안한다)

> ​		boolean equalsIgnoreCase = StringUtils.equalsIgnoreCase("ss", "sS");
>
> ​		System.out.println(equalsIgnoreCase);
>
> ​		//출력결과 : ture

​		

**StringUtils.firstNonBlank(문자열,문자열,문자열)**

null,공백,띄어쓰기를 제외한 첫번째 문자열을 가져온다

StringUtils **3.8**버전부터 사용가능

> ​		String firstNonBlank = StringUtils.firstNonBlank(null, "", " ", "xyz");
>
>    System.out.println(firstNonBlank);
>
> ​		출력결과 : xyz

​		

**StringUtils.getCommonPrefix(new String[] {"문자열", "문자열"})**

모든 문자열에서 공통된 첫부분을 출력한다.

> ​		String getCommonPrefix = StringUtils.getCommonPrefix("sss","ssS","ssa");
>
> ​		System.out.println(getCommonPrefix);
>
> ​		//출력결과 : ss

​		

**StringUtils.getDigits("문자열")**

Unicode Number(숫자)만 출력한다.

> ​		String getDigits = StringUtils.getDigits("123제거된다456");
>
> ​		System.out.println(getDigits);
>
> ​		//출력결과 : 123456

​		

**StringUtils.indexOf("문자열","찾을문자열")**

문자열중에 찾을 문자열이 포함된 첫번째 인덱스를 반환한다.

> ​		int indexOf = StringUtils.indexOf("sS", "S"); 
>
> ​		System.out.println(indexOf);
>
> ​		//출력결과 : 1



**StringUtils.indexOfAny("문자열",new String[] {"문자열", "문자열"})**

문자열과 배열을 비교하고(vararg형식) 첫번째 인덱스를 반환한다.

> ​		int indexOfAny = StringUtils.indexOfAny("안녕하세요",new String[] {"안", "녕"});
>
> ​		System.out.println(indexOfAny);
>
> ​		//출력결과 : 0

​		

**StringUtils.indexOfAnyBut("문자열",new char[] {'문자', '문자'})**

문자열과 문자 배열을 비교 후 배열에 없는 첫번째 문자인덱스를 반환한다.

> ​		int indexOfAnyBut = StringUtils.indexOfAnyBut("문자열",new char[] {'문', '자'});
>
> ​		System.out.println(indexOfAnyBut);
>
> ​		//출력결과 : 2

​		

**StringUtils.indexOfDifference("문자열","비교문자열");**

문자열과 비교문자열을 비교하고 달라지는 부분의 인덱스를 반환한다.

> ​		int indexOfDifference = StringUtils.indexOfDifference("안녕하세요","안녕하시오");
>
> ​		System.out.println(indexOfDifference);
>
> ​		//출력결과 : 3

​		

**StringUtils.indexOfIgnoreCase("문자열","찾을문자열")**

문자열중에 찾을 문자열이 포함된 첫번째 인덱스를 반환한다.(대/소문자를 구분안한다)

> ​		int indexOfIgnoreCase = StringUtils.indexOfIgnoreCase("sS", "S"); 
>
> ​		System.out.println(indexOfIgnoreCase);
>
> ​		//출력결과 : 0

**StringUtils.isAllBlank("문자열","문자열")**

모든 문자열이 "",null," "(공백)이면 true를 반환한다.

> ​		boolean isAllBlank = StringUtils.isAllBlank(" ",null);
>
> ​		System.out.println(isAllBlank);
>
> ​		//출력결과 : true



**StringUtils.isAllEmpty("문자열","문자열")**

모든 문자열이 "",null이면 true를 반환한다.

> ​		boolean isAllEmpty = StringUtils.isAllEmpty("",null);
>
> ​		System.out.println(isAllEmpty);
>
> ​		//출력결과 : true

​		

**StringUtils.isAllLowerCase("문자열")**

문자열이 소문자이면 true를 반환한다.	

> ​		boolean isAllLowerCase = StringUtils.isAllLowerCase("show");
>
> ​		System.out.println(isAllLowerCase);
>
> ​		//출력결과 : true



**StringUtils.isAllUpperCase("문자열")**

문자열이 대문자이면 true를 반환한다.	

> ​		boolean isAllUpperCase = StringUtils.isAllUpperCase("SHOW");
>
> ​		System.out.println(isAllUpperCase);
>
> ​		//출력결과 : true



**StringUtils.isAlpha("문자열")**

문자열이 문자로 구성되어있으면 true를 반환한다(숫자,특수문자,공백제외).

> ​		boolean isAlpha = StringUtils.isAlpha("show미더money");
>
> ​		System.out.println(isAlpha);
>
> ​		//출력결과 : true



**StringUtils.isAlphanumeric("문자열")**

문자열이 문자,숫자로 구성되어있으면 true를 반환한다(특수문자,공백제외).

> ​		boolean isAlphanumeric = StringUtils.isAlphanumeric("show미더money");
>
> ​		System.out.println(isAlphanumeric);
>
> ​		//출력결과 : true

​		

**StringUtils.isAlphanumericSpace("문자열")**

문자열이 문자,숫자,공백으로 구성되어있으면 true를 반환한다(특수문자제외).

> ​		boolean isAlphanumericSpace = StringUtils.isAlphanumericSpace("show 미 더 money");
>
> ​		System.out.println(isAlphanumericSpace);
>
> ​		//출력결과 : true

​		

**StringUtils.isAlphaSpace("문자열")**

문자열이 문자,공백으로 구성되어있으면 true를 반환한다(숫자,특수문자제외).

> ​		boolean isAlphaSpace = StringUtils.isAlphaSpace("show 미 더 money");
>
> ​		System.out.println(isAlphaSpace);
>
> ​		//출력결과 : true

​		

**StringUtils.isAnyBlank("문자열","문자열")**

문자열들중 "",null,공백이 하나라도 있으면 true를 반환한다.

vararg형식이므로 배열도 가능하다.

new String[] {} 배열안에 값이 하나도 없다면 false를 반환한다.

> ​		boolean isAnyBlank = StringUtils.isAnyBlank(new String[] {" ","가"});
>
> ​		System.out.println(isAnyBlank);
>
> ​		//출력결과 : true

​		

**StringUtils.isAnyEmpty("문자열","문자열")**

문자열들중 "",null이 하나라도 있으면 true를 반환한다.

vararg형식이므로 배열도 가능하다.

new String[] {} 배열안에 값이 하나도 없다면 false를 반환한다.

> ​		boolean isAnyEmpty = StringUtils.isAnyEmpty(new String[] {"","가"});
>
> ​		System.out.println(isAnyEmpty);
>
> ​		//출력결과 : true







**StringUtils.isAsciiPrintable("문자열")**

ASCII 인쇄가능한 문자만 있을경우 true를 반환한다.

> ​		boolean isAsciiPrintable = StringUtils.isAsciiPrintable("show");
>
> ​		System.out.println(isAsciiPrintable);
>
> ​		//출력결과 : true

​		

**StringUtils.isBlank("문자열")**

문자열이 "",null,공백이라면 true를 반환한다.

> ​		boolean isBlank = StringUtils.isBlank(" ");
>
> ​		System.out.println(isBlank);
>
> ​		//출력결과 : true



**StringUtils.isEmpty("문자열")**

문자열이 "",null라면 true를 반환한다.

> ​		boolean isEmpty = StringUtils.isEmpty("");
>
> ​		System.out.println(isEmpty);
>
> ​		//출력결과 : true

​		

**StringUtils.isMixedCase("문자열")**

문자열이 대/소문자가 혼합되어있으면 true를 반환한다.

> ​		boolean isMixedCase = StringUtils.isMixedCase("Show");
>
> ​		System.out.println(isMixedCase);
>
> ​		//출력결과 : true

​		

**StringUtils.isNoneBlank("문자열","문자열")**

문자열들에 "",null,공백이 없다면 true를 반환한다.

vararg형식이므로 배열도 가능하다.

new String[] {} 배열안에 값이 하나도 없다면 true를 반환한다.

> ​		boolean isNoneBlank = StringUtils.isNoneBlank("Show","me");
>
> ​		System.out.println(isNoneBlank);
>
> ​		//출력결과 : true

​		

**StringUtils.isNoneEmpty("문자열","문자열")**

문자열들에 "",null이 없다면 true를 반환한다.

vararg형식이므로 배열도 가능하다.

new String[] {} 배열안에 값이 하나도 없다면 true를 반환한다.

> ​		boolean isNoneEmpty = StringUtils.isNoneEmpty("Show","me");
>
> ​		System.out.println(isNoneEmpty);
>
> ​		//출력결과 : true

​		

**StringUtils.isNotBlank("문자열")**

문자열이 "",null,공백이 아니라면 true를 반환한다.

> ​		boolean isNotBlank = StringUtils.isNotBlank("Show");
>
> ​		System.out.println(isNotBlank);
>
> ​		//출력결과 : true

​		

**StringUtils.isNotEmpty("문자열")**

문자열이 "",null이 아니라면 true를 반환한다.

> ​		boolean isNotEmpty = StringUtils.isNotEmpty(" ");
>
> ​		System.out.println(isNotEmpty);
>
> ​		//출력결과 : true

​		

**StringUtils.isNumeric("문자열")**

문자열이 숫자라면 true를 반환한다.

음수는 인식하지 못한다.

> ​		boolean isNumeric = StringUtils.isNumeric("123");
>
> ​		System.out.println(isNumeric);
>
> ​		//출력결과 : true

​		

**StringUtils.isNumericSpace("문자열")**

문자열이 띄어쓰기를 포함한 숫자이거나 그냥 숫자라면 true를 반환한다.

음수는 인식하지 못한다.

> ​		boolean isNumericSpace = StringUtils.isNumericSpace("1 2 3");
>
> ​		System.out.println(isNumericSpace);
>
> ​		//출력결과 : true

​		

**StringUtils.isWhitespace("문자열")**

문자열이 "",공백이라면 true를 반환한다.

> ​		boolean isWhitespace = StringUtils.isWhitespace(" ");
>
> ​		System.out.println(isWhitespace);
>
> ​		//출력결과 : true

​		

**StringUtils.startsWith("문자열","시작문자열")**

문자열의 시작이 시작문자열과 같다면 true를 반환한다.

문자열과 시작문자열이 null,null이여도 true를 반환한다.

> ​		boolean startsWith = StringUtils.startsWith("ShowMeTheMoney", "Show");
>
> ​		System.out.println(startsWith);
>
> ​		//출력결과 : true

​		

**StringUtils.startsWithAny("문자열","시작문자열","시작문자열")**

문자열의 시작이 시작문자열중 하나라도 같다면 true를 반환한다.

vararg형식이므로 배열도 가능하다.

new String[] {} 배열안에 값이 하나도 없다면 true를 반환한다.

> ​		boolean startsWithAny = StringUtils.startsWithAny("ShowMeTheMoney", new String[] {null, "xyz", "Show"});
>
> ​		System.out.println(startsWithAny);
>
> ​		//출력결과 : true

​		

**StringUtils.startsWithIgnoreCase("문자열","시작문자열")**

문자열의 시작이 시작문자열이 같다면 true를 반환한다.(대/소문자를 구분안한다)

> ​		boolean startsWithIgnoreCase = StringUtils.startsWithIgnoreCase("ShowMeTheMoney", "show");
>
> ​		System.out.println(startsWithIgnoreCase);
>
> ​		//출력결과 : true

​		

**StringUtils.join(각종배열,"구분자")**

여러종류의 배열을 구분자로 구분한 문자열을 반환해준다.

구분자가 없을경우 배열을 문자열 형태로 바꿔준다.

"",null은 ""로 표시된다.

> ​		String join = StringUtils.join( new String[] {"show", "me", "the","money"}, "*");
>
> ​		System.out.println(join);
>
> ​		//출력결과 : show*me*the*money

​		

**StringUtils.joinWith("구분자",각종배열)**

여러종류의 배열을 구분자로 구분한 문자열을 반환해준다.

구분자가 없을경우 배열을 문자열 형태로 바꿔준다.

"",null은 ""로 표시된다.

> ​		String joinWith = StringUtils.joinWith("*", new String[] {"show", "me", "the","money"});
>
> ​		System.out.println(joinWith);
>
> ​		//출력결과 : show*me*the*money



**StringUtils.lastIndexOf("문자열","찾을문자열")**

문자열에서 찾을 문자열을 확인 후 마지막 문자열의 위치를 반환한다.

문자열이 "",null이면 -1을 반환한다.

> ​		int lastIndexOf = StringUtils.lastIndexOf("aaaaaaaaaa", "a");
>
> ​		System.out.println(lastIndexOf);
>
> ​		//출력결과 : 9

​		

**StringUtils.lastIndexOf("문자열","찾을문자열",검색범위(int형))**

문자열에서 검색범위안에서 찾을 문자열을 확인 후 마지막 문자열의 위치를 반환한다.

문자열이 "",null이면 -1을 반환한다.

> ​		int lastIndexOf2 = StringUtils.lastIndexOf("aaaaaaaaaa", "a", 5);
>
> ​		System.out.println(lastIndexOf2);
>
> ​		//출력결과 : 5



**StringUtils.lastIndexOfAny("문자열","찾을문자열","찾을문자열")**

문자열에서 검색범위안에서 찾을 문자열을 확인 후 마지막 문자열의 위치를 반환한다.

문자열이 "",null이면 -1을 반환한다.

찾을문자열에 같은 문자열이 없고 찾을문자열에 공백이 있을 경우 문자열의 크기를 반환한다.

vararg형식이므로 배열도 가능하다.

new String[] {} 배열안에 값이 하나도 없다면 -1를 반환한다.

> ​		int lastIndexOfAny = StringUtils.lastIndexOfAny("aaaaa", new String[] {"a","b"});
>
> ​		System.out.println(lastIndexOfAny);
>
> ​		//출력결과 : 4

​		

**StringUtils.lastIndexOfIgnoreCase("문자열","찾을문자열")**

문자열에서 찾을 문자열을 확인 후 마지막 문자열의 위치를 반환한다.(대/소문자를 구분안한다)

문자열이 "",null이면 -1을 반환한다.

> ​		int lastIndexOfIgnoreCase = StringUtils.lastIndexOfIgnoreCase("aaaaaaaaaa", "A");
>
> ​		System.out.println(lastIndexOfIgnoreCase);
>
> ​		//출력결과 : 6

​		

**StringUtils.lastIndexOfIgnoreCase("문자열","찾을문자열")**

문자열에서 검색범위안에서 찾을 문자열을 확인 후 마지막 문자열의 위치를 반환한다.(대/소문자를 구분안한다)

문자열이 "",null이면 -1을 반환한다.

> ​		int lastIndexOfIgnoreCase2 = StringUtils.lastIndexOfIgnoreCase("aaaaaaaaaa", "A",5);
>
> ​		System.out.println(lastIndexOfIgnoreCase2);
>
> ​		//출력결과 : 5

​		

**StringUtils.lastIndexOfIgnoreCase("문자열","찾을문자열",검색시작숫자(int형))**

문자열에서 검색시작숫자부터 찾을 문자열을 확인 후 마지막 문자열의 위치를 반환한다.(1부터 시작한다)

문자열이 "",null이면 -1을 반환한다.

> ​		int lastOrdinalIndexOf = StringUtils.lastOrdinalIndexOf("aaaaaaaaaa", "a", 4);
>
> ​		System.out.println(lastOrdinalIndexOf);
>
> ​		//출력결과 : 9



**StringUtils.left("문자열",시작할위치(int형))**

시작할 위치 기준으로 왼쪽글자를 가져온다.

> ​		String left = StringUtils.left("show", 2);
>
> ​		System.out.println(left);
>
> ​		//출력결과 : sh

​		

**StringUtils.left("문자열",문자열크기,"추가단어")**

문자열 크기만큼 왼쪽에 추가단어를 생성한다.

추가단어가 없을경우 공백을 추가한다.

> ​		String leftPad = StringUtils.leftPad("show", 10, "*");
>
> ​		System.out.println(leftPad);
>
> ​		//출력결과 : ******show

**
**

**StringUtils.length("문자열")**

문자열의 크기를 반환한다(1부터시작한다).

null,""이면 0을 반환한다.

> ​		int length = StringUtils.length("show");
>
> ​		System.out.println(length);
>
> ​		//출력결과 : 4

**StringUtils.length("문자열")**

문자열을 소문자로 반환한다.

> ​		String lowerCase = StringUtils.lowerCase("SHOW");
>
> ​		System.out.println(lowerCase);
>
> ​		//출력결과 : show

**StringUtils.mid("문자열",시작위치,가져올길이)**

문자열을 입력된 시작위치에서 가져올길이 만큼가져온다

> ​		String mid = StringUtils.mid("showmethemoney", 4, 5);
>
> ​		System.out.println(mid);
>
> ​		//출력결과 : methe

**StringUtils.normalizeSpace("문자열")**

문자열의 앞뒤 공백을 제거하고 중간에 여러 공백문자를 제거한다.

> ​		String normalizeSpace = StringUtils.normalizeSpace("show \tme the money");
>
> ​		System.out.println(normalizeSpace);
>
> ​		//출력결과 : show me the money

​		

**StringUtils.ordinalIndexOf("문자열","찾을문자열",카운트수)**

문자열에서 찾을문자열을 찾고 카운트하다 카운수에 만족한 위치를 반환한다.

null이거나 카운트수에 만족한 문자가 없을경우 -1을 반환한다.

> ​		int ordinalIndexOf = StringUtils.ordinalIndexOf("abcabcabcabc", "abc", 3);
>
> ​		System.out.println(ordinalIndexOf);
>
> ​		//출력결과 : 6

​		

**StringUtils.overlay("문자열","넣을문자열",시작위치, 끝위치)**

문자열안에 시작위치부터 끝위치전까지 넣을 문자열로 변환한다.

> ​		String overlay = StringUtils.overlay("0123456789", "**", 2, 7);
>
> ​		System.out.println(overlay);
>
> ​		//출력결과 : 01**789

**StringUtils.prependIfMissing("문자열","접두사","부가접두사")**

문자열이 접두사나 부가접두사로 시작하지 않을경우 접두사를 추가한다.

> ​		String prependIfMissing = StringUtils.prependIfMissing("Show", "me", "the");
>
> ​		System.out.println(prependIfMissing);
>
> ​		//출력결과 : meShow

**StringUtils.prependIfMissing("문자열","접두사","부가접두사")**

문자열이 접두사나 부가접두사로 시작하지 않을경우 접두사를 추가한다.(대/소문자를 구분안한다)

> ​		String prependIfMissingIgnoreCase = StringUtils.prependIfMissingIgnoreCase("Show", "me", "show");
>
> ​		System.out.println(prependIfMissingIgnoreCase);
>
> ​		//출력결과 : Show

​		

**StringUtils.remove("문자열","제거할문자")**

문자열안에 제거할 문자가 있을경우 제거하여 반환한다(반복가능).

> ​		String remove = StringUtils.remove("s**h**o**w", "**");
>
> ​		System.out.println(remove);
>
> ​		//출력결과 : show

**StringUtils.removeAll("문자열","정규식")**

문자열안에 정규식에 포함하는 문자가 있을경우 제거하여 반환한다.

> ​		String removeAll = StringUtils.removeAll("showMETHEMONEY", "[A-Z]");
>
> ​		System.out.println(removeAll);
>
> ​		//출력결과 : show

**StringUtils.removeEnd("문자열","제거할문자")**

문자열 마지막에 제가할문자가 있을경우 제거한다.

> ​		String removeEnd = StringUtils.removeEnd("showME","ME");
>
> ​		System.out.println(removeEnd);
>
> ​		//출력결과 : show

**StringUtils.removeEndIgnoreCase("문자열","제거할문자")**

문자열 마지막에 제가할문자가 있을경우 제거한다.(대/소문자를 구분안한다)

> ​		String removeEndIgnoreCase = StringUtils.removeEndIgnoreCase("showME", "me");
>
> ​		System.out.println(removeEndIgnoreCase);
>
> ​		//출력결과 : show

**StringUtils.removeFirst("문자열","정규식")**

문자열안에 정규식에 포함하는 문자가 있을경우 첫번째를 제거하여 반환한다.

> ​		String removeFirst = StringUtils.removeFirst("<test>show", "<.*>");
>
> ​		System.out.println(removeFirst);
>
> ​		//출력결과 : show

**StringUtils.removeIgnoreCase("문자열","제거할문자")**

문자열안에 제거할 문자가 있을경우 제거하여 반환한다(반복가능).(대/소문자를 구분안한다)

> ​		String removeIgnoreCase = StringUtils.removeIgnoreCase("sThtotwT", "t");
>
> ​		System.out.println(removeIgnoreCase);
>
> ​		//출력결과 : show

**StringUtils.removePattern("문자열","제거할패턴")**

문자열안에 제거할 패턴이 있을경우 패턴안의 내용까지 제거후 반환한다.

> ​		String removePattern = StringUtils.removePattern("<test>\n<test>show", "<.*>");
>
> ​		System.out.println(removePattern);
>
> ​		//출력결과 : show

**StringUtils.removeStart("문자열","제거할문자")**

문자열안에 첫번쨰 제거할 문자를 제거한 후 반환한다.

> ​		String removeStart = StringUtils.removeStart("showshow", "show");
>
> ​		System.out.println(removeStart);
>
> ​		//출력결과 : show

​		

**StringUtils.removeStartIgnoreCase("문자열","제거할문자")**

문자열안에 첫번쨰 제거할 문자를 제거한 후 반환한다.(대/소문자를 구분안한다)

> ​		String removeStartIgnoreCase = StringUtils.removeStartIgnoreCase("showshow", "SHOW");
>
> ​		System.out.println(removeStartIgnoreCase);
>
> ​		//출력결과 : show

​		

**StringUtils.repeat("문자열","구분자",반복할숫자)**

문자열을 반복할 숫자만큼 반복하여 반환한다.

구분자가 없을경우 그냥 반복하여 반환한다.

> ​		String repeat = StringUtils.repeat("show",",", 3);
>
> ​		System.out.println(repeat);
>
> ​		//출력결과 : show,show,show

​		

**StringUtils.replace("문자열","찾을문자","변경문자")**

문자열에서 찾을 문자열을 찾고 변경문자로 변경하여 반환한다.

> ​		String replace = StringUtils.replace("testtest", "test", "show");
>
> ​		System.out.println(replace);
>
> ​		//출력결과 : showshow

**StringUtils.replace("문자열","찾을문자","변경문자",변경횟수)**

문자열에서 찾을 문자열을 찾고 변경횟수만큼 변경문자로 변경하여 반환한다.

> ​		String replace2 = StringUtils.replace("testtest", "test", "show",1);
>
> ​		System.out.println(replace2);
>
> ​		//출력결과 : showtest

**StringUtils.replaceAll("문자열","정규식","변경문자")**

문자열에서 정규식에 포함되는 문자를 찾고 

변경문자로 변경하여 반환한다.

> ​		String replaceAll = StringUtils.replaceAll("SHOWshowSHOW", "[A-Z]", "^");
>
> ​		System.out.println(replaceAll);
>
> ​		//출력결과 : ^^^^show^^^^

**StringUtils.replaceChars("문자열","변경할문자","변경문자")**

문자열에서 변경할 문자를 한글자씩 찾고 변경문자로 변경한다.

> ​		String replaceChars = StringUtils.replaceChars("mhoe", "me", "sw");
>
> ​		System.out.println(replaceChars);
>
> ​		//출력결과 : show

​		

**StringUtils.replaceEach("문자열",변경할문자배열,변경문자배열)**

문자열에서 변경할 문자배열을 확인후 있으면 변경문자배열로 변경하여 반환한다.

> ​		String replaceEach =
>
> ​		StringUtils.replaceEach("methe", new String[]{"me", "the"}, new String[]{"sh", "ow"});
>
> ​		System.out.println(replaceEach);
>
> ​		//출력결과 : show

**StringUtils.replaceEachRepeatedly("문자열",변경할문자배열,변경문자배열)**

문자열에서 변경할 문자배열을 확인후 그 단어를 변경문자배열에 확인하여

변경문자배열과 겹치지 않은 단어로 변경한다.

쓸일없을거같다.

> ​		String replaceEachRepeatedly = 
>
> ​		StringUtils.replaceEachRepeatedly("me", new String[]{"m", "e"}, new String[]{"e", "d"});
>
> ​		System.out.println(replaceEachRepeatedly);
>
> ​		//출력결과 : dd

​		

**StringUtils.replaceFirst("문자열","찾을문자열","변경문자")**

문자열에서 찾을문자열을 찾아 첫번째를 변경문자로 변경 후 반환한다.(정규식사용가능)

> ​		String replaceFirst = StringUtils.replaceFirst("show56show", "show", "1234");
>
> ​		System.out.println(replaceFirst);
>
> ​		//출력결과 : 123456show

​		

**StringUtils.replaceFirst("문자열","찾을문자열","변경문자")**

문자열에서 찾을문자열을 찾아 변경문자로 변경 후 반환한다.(대/소문자를 구분안한다)

> ​		String replaceIgnoreCase = StringUtils.replaceIgnoreCase("Aa", "a", "1");
>
> ​		System.out.println(replaceIgnoreCase);
>
> ​		//출력결과 : 11

​	

**StringUtils.replaceOnce("문자열","찾을문자열","변경문자")**

문자열에서 찾을문자열을 찾아 한번만 변경문자로 변경 후 반환한다.(정규표현식사용불가)

> ​		String replaceOnce = StringUtils.replaceOnce("sshow", "s", "1");
>
> ​		System.out.println(replaceOnce);
>
> ​		//출력결과 : 1show

​		

**StringUtils.replaceOnceIgnoreCase("문자열","찾을문자열","변경문자")**

문자열에서 찾을문자열을 찾아 한번만 변경문자로 변경 후 반환한다.(대/소문자를 구분안한다,정규표현식사용불가)

> ​		String replaceOnceIgnoreCase = StringUtils.replaceOnceIgnoreCase("sshow", "S", "1");
>
> ​		System.out.println(replaceOnceIgnoreCase);
>
> ​		//출력결과 : 1show

​	

**StringUtils.replacePattern("문자열","정규식","변경문자")**

문자열에서 정규식에 포함되어있는 문자를 변경문자로 변경 후 반환한다.

> ​		String replacePattern = StringUtils.replacePattern("<__>test<__>me", "<.*>", "show");
>
> ​		System.out.println(replacePattern);
>
> ​		//출력결과 : showme

**StringUtils.reverse("문자열")**

문자열을 반대로 변환후 반환한다.

> ​		String reverse = StringUtils.reverse("show");
>
> ​		System.out.println(reverse);
>
> ​		//출력결과 : wohs

​		

**StringUtils.reverse("문자열",'구분자'(char형태문자))**

구분자 기준으로 순서를 반대로 바꾼후 반환한다.

구분자가 아닌 문자는 반대로 변환되지 않는다.

> ​		String reverseDelimited = StringUtils.reverseDelimited("123.456.789", '.');
>
> ​		System.out.println(reverseDelimited);
>
> ​		//출력결과 : 789.456.123

**StringUtils.right("문자열",가져올크기)**

문자열의 오른쪽을 기준으로 가져올크기 만큼 반환한다.

> ​		String right = StringUtils.right("show", 2);
>
> ​		System.out.println(right);
>
> ​		//출력결과 : ow

​	

**StringUtils.rightPad("문자열",문자크기,"추가할문자")**

문자열의 오른쪽에 문자크기만큼 추가할문자를 추가 후 반환한다.

추가할문자가 없을 경우 공백으로 추가 후 반환환다.

> ​		String rightPad = StringUtils.rightPad("show", 10, "!@#$");
>
> ​		System.out.println(rightPad);
>
> ​		//출력결과 : show!@#$!@

**StringUtils.rotate("문자열",이동할숫자)**

문자열을 이동할숫자만큼 이동한다 (양수방향 ->,음수방향<-)

> ​		String rotate = StringUtils.rotate("show", 2);
>
> ​		System.out.println(rotate);
>
> ​		//출력결과 : owsh

**StringUtils.split("문자열")**

문자열의 공백을 기준으로 나눈다(배열).

> ​		String[] split = StringUtils.split("123 456 789");
>
> ​		for (String string : split) {
>
> ​			System.out.print(string+"!");
>
> ​		}
>
> ​		//출력결과 : 123!456!789!



**StringUtils.split("문자열","구분자")**

문자열의 구분자를 기준으로 나눈다(배열).

구분자가 null일시 공백을 기준으로 나눈다.

> ​		String[] split2 = StringUtils.split("123@!@456@!@789","@!@");
>
> ​		for (String string : split) {
>
> ​			System.out.print(string+"!");
>
> ​		}
>
> ​		//출력결과 : 123!456!789!



**StringUtils.splitByCharacterType("문자열")**

**문자열을 동일한 문자열(대/소문자,한글,숫자등) 기준으로 나눈다(배열).**

> ​		String[] splitByCharacterType = 
>
> ​				StringUtils.splitByCharacterType("show ME the Money 10000");
>
> ​		for (String string : splitByCharacterType) {
>
> ​			System.out.print(string+"!");
>
> ​		}
>
> ​		//출력결과 : show! !ME! !the! !M!oney! !10000!



**StringUtils.splitByCharacterType("문자열")**

문자열을 동일한 문자열(대/소문자,한글,숫자등) 기준으로 나눈다(배열).

단 카멜케이스 즉 대문자로 시작하는 문자열은 한단어로 생각한다.

> ​		String[] splitByCharacterTypeCamelCase = 
>
> ​		StringUtils.splitByCharacterTypeCamelCase("show ME the Money 10000");
>
> ​		for (String string : splitByCharacterTypeCamelCase) {
>
> ​			System.out.print(string+"!");
>
> ​		}
>
> ​		//출력결과 : show! !ME! !the! !Money! !10000!



**StringUtils.splitByWholeSeparator("문자열","구분자")**

문자열의 구분자를 기준으로 나눈다(배열).

구분자가 null일시 공백을 기준으로 나눈다.

> ​		String[] splitByWholeSeparator =
>
> ​		StringUtils.splitByWholeSeparator("show ME the Money 10000", null);
>
> ​		for (String string : splitByWholeSeparator) {
>
> ​			System.out.print(string+"!");
>
> ​		}
>
> ​		//출력결과 : show!ME!the!Money!10000!



**StringUtils.splitByWholeSeparatorPreserveAllTokens("문자열","구분자")**

문자열의 구분자를 기준으로 나눈다(배열).

구분자가 null일시 공백을 기준으로 나눈다.

공백을 기준으로 나눌시 공백이 여러개일경우 하나를 제외하곤 문자로 포함된다.

> ​		String[] splitByWholeSeparatorPreserveAllTokens =
>
> ​		StringUtils.splitByWholeSeparatorPreserveAllTokens("123 456 789", null);
>
> ​		for (String string : splitByWholeSeparatorPreserveAllTokens) {
>
> ​			System.out.print(string+"!");
>
> ​		}
>
> ​		//출력결과 : 123!!456!789!



**StringUtils.splitPreserveAllTokens("문자열")**

문자열을 공백을 기준으로 나눈다(배열).

공백이 여러개일경우 하나를 제외하곤 문자로 포함된다.

> ​		String[] splitPreserveAllTokens =
>
> ​		StringUtils.splitPreserveAllTokens("123 456 789");
>
> ​		for (String string : splitPreserveAllTokens) {
>
> ​			System.out.print(string+"!");
>
> ​		}
>
> ​		//출력결과 : 123!!456!789!



**StringUtils.splitPreserveAllTokens("문자열","구분자")**

문자열의 구분자를 기준으로 나눈다(배열).

문자열에 앞뒤로 구분자가 있을경우 빈값으로 배열에 포함한다.

> ​		String[] splitPreserveAllTokens2 =
>
> ​		StringUtils.splitPreserveAllTokens("@123@ 456@789 ","@");
>
> ​		for (String string : splitPreserveAllTokens2) {
>
> ​			System.out.print(string+"!");
>
> ​		}
>
> ​		//출력결과 : !123! 456!789 !



**StringUtils.strip("문자열","문자")**

문자열의 앞뒤 문자를 제거한다.

문자가 없을경우 앞뒤 공백을 제거한다.

> ​		String strip = StringUtils.strip("@!show@!me@!","@!");
>
> ​		System.out.println(strip);
>
> ​		//출력결과 : show me

​	

**StringUtils.stripAccents("문자열")**

문자열에 표시된 억양을 제거한다.

> ​		String stripAccents = StringUtils.stripAccents("à");
>
> ​		System.out.println(stripAccents);
>
> ​		//출력결과 : a



**StringUtils.stripAll(문자배열,"문자")**

문자배열안의 모든 문자열 앞뒤 문자를 제거한다.

문자가 없을경우 앞뒤 공백을 제거한다.

> ​		String[] stripAll = 
>
> ​				StringUtils.stripAll(new String[] {"@1@2@3@", "@4@5@6@"},"@");
>
> ​		for (String string : stripAll) {
>
> ​			System.out.print(string+"!");
>
> ​		}
>
> ​		//출력결과 : 1@2@3!4@5@6!









**StringUtils.stripEnd("문자열","문자")**

문자열의 뒷부분에 문자를 제거한다.

문자가 없을경우 뒷부분 공백을 제거한다.

> ​		String stripEnd = StringUtils.stripEnd("@1@2@3@","@");
>
> ​		System.out.println(stripEnd);
>
> ​		//출력결과 : @1@2@3

​	

**StringUtils.stripStart("문자열","문자")**

문자열의 앞부분에 문자를 제거한다.

문자가 없을경우 앞부분 공백을 제거한다.

> ​		String stripStart = StringUtils.stripStart("@1@2@3@","@");
>
> ​		System.out.println(stripStart);
>
> ​		//출력결과 : 1@2@3@



​		

**StringUtils.stripToEmpty("문자열")**

문자열의 앞뒤 공백을 제거한다.

문자열이 null,"","  "이면 ""로 반환환다.

> ​		String stripToEmpty = StringUtils.stripToEmpty("  1 2 3  ");
>
> ​		System.out.println(stripToEmpty);
>
> ​		//출력결과 : 1 2 3

​		

**StringUtils.stripToNull("문자열")**

문자열의 앞뒤 공백을 제거한다.

문자열이 null,"","  "이면 null로 반환환다.

> ​		String stripToNull = StringUtils.stripToNull("  1 2 3  ");
>
> ​		System.out.println(stripToNull);

​		

**StringUtils.substring("문자열",시작위치)**

문자열의 시작위치 순서부터 반환한다.

> ​		String substring = StringUtils.substring("0123456", 3);
>
> ​		System.out.println(substring);
>
> ​		//출력결과 : 3456

​		

**StringUtils.substring("문자열",시작위치,종료위치)**

문자열의 시작위치 순서부터 종료위치전까지 반환한다.

> ​		String substring2 = StringUtils.substring("0123456", 3, 5);
>
> ​		System.out.println(substring2);
>
> ​		//출력결과 : 34

​		

**StringUtils.substringAfter("문자열","시작문자")**

문자열에서 시작문자를 찾고 그다음부터 반환한다.

> ​		String substringAfter = StringUtils.substringAfter("0123456", "3");
>
> ​		System.out.println(substringAfter);
>
> ​		//출력결과 : 456

​		

**StringUtils.substringAfterLast("문자열","시작문자")**

문자열에서 시작문자를 찾고 마지막 시작문자 그다음부터 반환한다.

> ​		String substringAfterLast = StringUtils.substringAfterLast("01230123", "1");
>
> ​		System.out.println(substringAfterLast);

​		

**StringUtils.substringBeforeLast("문자열","시작문자")**

문자열에서 시작문자를 찾고 마지막 시작문자 그앞에 문자들을 반환한다.

> ​		String substringBeforeLast = StringUtils.substringBeforeLast("01230123", "1");
>
> ​		System.out.println(substringBeforeLast);
>
> ​		//출력결과 : 01230

​		

**StringUtils.substringBetween("문자열","태그문자")**

문자열에서 태그문자를 찾고 태그문자 사이의 값을 반환한다.

> ​		String substringBetween = StringUtils.substringBetween("<tag>ss<tag>", "<tag>");
>
> ​		System.out.println(substringBetween);

​		

**StringUtils.substringBetween("문자열","태그문자", "태그종료문자")**

문자열에서 태그문자와 태그종료문자를 찾고 태그문자 사이의 값을 반환한다.

> ​		String substringBetween2 = 
>
> ​				StringUtils.substringBetween("<tag>ss</tag>", "<tag>", "</tag>");
>
> ​		System.out.println(substringBetween2);
>
> ​		//출력결과 : ss

​		

**StringUtils.substringsBetween("문자열","태그문자","태그종료문자")**

문자열에서 태그문자를 찾고 태그문자 사이의 값을 배열로 반환한다.

> ​		String[] substringsBetween = 
>
> ​				StringUtils.substringsBetween("[1],[2],[3]", "[", "]");
>
> ​		for (String string : substringsBetween) {
>
> ​			System.out.print(string+"!");
>
> ​		}
>
> ​		//출력결과 : 1!2!3!

​		

**StringUtils.swapCase("문자열")**

문자열의 대문자는 소문자 소문자는 대문자로 변환한다.

> ​		String swapCase = StringUtils.swapCase("sHOW");
>
> ​		System.out.println(swapCase);
>
> ​		//출력결과 : Show

​		

**StringUtils.toCodePoints("문자열")**

문자열을 코드포인트형태로 변환하여 int배열로 반환한다.

> ​		int[] toCodePoints = StringUtils.toCodePoints("int");
>
> ​		System.out.println(toCodePoints);
>
> ​		for (int num : toCodePoints) {
>
> ​			System.out.print(num+"!");
>
> ​		}
>
> ​		//출력결과 : 105!110!116!

​		

**StringUtils.trim("문자열")**

문자열의 앞뒤공백을 제거한다.

> ​		String trim = StringUtils.trim(" s h o w ");
>
> ​		System.out.println(trim);
>
> ​		//출력결과 : s h o w

​		

**StringUtils.trimToEmpty("문자열")**

문자열의 앞뒤공백을 제거한다

문자열이 null,"","  "이면 ""로 반환환다.

> ​		String trimToEmpty = StringUtils.trimToEmpty(" show ");
>
> ​		System.out.println(trimToEmpty);
>
> ​		//출력결과 : s h o w

​		

**StringUtils.trimToNull("문자열")**

문자열의 앞뒤공백을 제거한다

문자열이 null,"","  "이면 null로 반환환다.

> ​		String trimToNull = StringUtils.trimToNull(" show ");
>
> ​		System.out.println(trimToNull);
>
> ​		//출력결과 : s h o w

​						

**StringUtils.trimToNull("문자열" ,잘라낼크기)**

문자열을 잘라낼크기만큼 잘라낸다.

> ​		String truncate = StringUtils.truncate("0123456", 4);
>
> ​		System.out.println(truncate);
>
> ​		//출력결과 : 0123

​		

**StringUtils.trimToNull("문자열" ,잘라낼시작크기,잘라낼종료크기)**

문자열을 잘라낼시작크기에서 종료크기만큼 잘라낸다.

> ​		String truncate2 = StringUtils.truncate("0123456", 1, 5);
>
> ​		System.out.println(truncate2);
>
> ​		//출력결과 : 12345

​		

**StringUtils.uncapitalize("문자열")**

문자열의 첫글자가 대문자이면 소문자로 변환한다.

> ​		String uncapitalize = StringUtils.uncapitalize("SHOW");
>
> ​		System.out.println(uncapitalize);
>
> ​		//출력결과 : sHOW

​		

**StringUtils.unwrap("문자열","문자")**

문자열이 문자로 감싸져있다면 풀어서 반환한다.

> ​		String unwrap = StringUtils.unwrap("!show!", "!");
>
> ​		System.out.println(unwrap);
>
> ​		//출력결과 : show



**StringUtils.unwrap("문자열")**

문자열을 대문자로 변경해서 반환한다

> ​		String upperCase = StringUtils.upperCase("show");
>
> ​		System.out.println(upperCase);
>
> ​		//출력결과 : SHOW



**StringUtils.wrap("문자열","문자")**

문자열이 문자로 감싸서 풀어서 반환한다.

> ​		String wrap = StringUtils.wrap("show", "!");
>
> ​		System.out.println(wrap);
>
> ​		//출력결과 : !show!

​		

**StringUtils.wrap("문자열","문자")**

문자열의 시작과 끝에 문자가 없으면 추가해서 반환한다.

> ​		String wrapIfMissing = StringUtils.wrapIfMissing("show!", "!");
>
> ​		System.out.println(wrapIfMissing);
>
> ​		//출력결과 : !show!


