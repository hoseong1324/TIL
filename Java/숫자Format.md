### 숫자 변환 ( DecimalFormat )

#### import java.text.DecimalFormat

```

    패턴				  의미

 ​	0				10진수, 빈자리는 0으로 채움

 ​	#				10진수, 빈자리는 채우지 않음

 ​	.				소수점 표시

 ​	,				단위 구분 기호 표시

 ​	+,-			음, 양수 표시

 ​	E				지수 문자

 ​	;				양수, 음수 두가지 사용할때 패턴 구분

 ​	%				100을 곱하고 %를 붙힘

 ​	|u00A4				통화표시 \를 붙힘
```


// 변환할 값 

double n = 12345.6789;  	 	

System.out.println("\n ======= 숫자형식 변환의 DecimalFormat 클래스 ======= \n"); 	 	

// 10진수 - 빈자리는 0으로 채움  	

DecimalFormat df = new DecimalFormat("0");  	

System.out.println(df.format(n)); // 출력값 : 12346 	 	

// 10진수 - 빈자리는 0으로 채움 	

df = new DecimalFormat("0.0");  	

System.out.println(df.format(n)); // 출력값 : 12345.7 	 	

// 10진수 - 빈자리는 0으로 채움 	

df = new DecimalFormat("000000.00000");  	

System.out.println(df.format(n)); // 출력값 : 012345.67890 	 	

// 10진수 - 빈자리는 채우지 않음 	

df = new DecimalFormat("#");  	

System.out.println(df.format(n)); // 출력값 : 12346 	 	

// 10진수 - 빈자리는 채우지 않음 	

df = new DecimalFormat("######.###"); 	

System.out.println(df.format(n)); // 출력값 : 12345.679 	 	

// 10진수 - # 0 조합 / 단위구분을 위한 , 추가 	

df = new DecimalFormat("#,###.00000"); 	

System.out.println(df.format(n)); // 출력값 : 12,345.67890 	 	

// 100을 곱한 후 문자에 % 붙임 	

df = new DecimalFormat("#.##%");  	

System.out.println(df.format(n)); // 출력값 : 1234567.89% 		

// 통화표시 \u00A4  	

df = new DecimalFormat("\u00A4####.##");  	

System.out.println(df.format(n)); // 출력값 : ￦12345.68 		

