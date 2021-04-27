### subString
* 사용법 
```
String.substring(start)  //문자열 start위치부터 끝까지 문자열 자르기 
String.substring(start,end) //문자열 start위치 부터 end전까지 문자열 발췌 
```
* 예제
```
String str = "ABCDEFG"; //대상 문자열
 /*A=0 B=1 C=2 D=3 E=4 F=5 G=6의 index를 가진다.*/

str.substring(3);
 /*substring(시작위치) 결과값 = DEFG*/ 

str.substring(3, 6); 
/*substring(시작위치,끝위치) 결과값 = DEF*/
```

### 현재시간 가져오기

```
SimpleDateFormat format = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
```
#### 응용
`Date date = format.parse(데이터);`     
하면 String인 데이터를 Date 형으로 변환    
출력하면      
#### Mon Sep 02 08:10:55 KST 2019      
처럼 나오는데 아래 처럼 다시한번 더 변환     
` String RegDate = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss").format(date);`      
하면 가져온 데이터를 정해놓은 시간 형식으로 변환하여 String 으로 출력 가능


* Date 이용
```
Date time = new Date();
			String time = format.format(time);
```
* Calendar 이용
```
Calendar time = Calendar.getInstance();
			String time = format.format(time);
```
			
* currentTimeMillis 이용
```
String format_time = format.format (System.currentTimeMillis());
String time = format.format(format_time);
```

#### 날짜형식
* yy-MM-dd = 21-04-21
* yyyy-MM-dd = 2021-04-21
* yyyy/MM/dd HH:mm:ss = 2021/04/21 14:54:25
* yyyy/MM/dd hh:mm:ss = 2021/04/21 pm 2:54:25


```
패턴 		 의미				출력
G	연대(BC, AD)				AD
y	년도					2017
M	월(1~12)				12
w	해당 년도의 몇 번째 주(1~53)		52
W	해당 월의 몇 번째 주(1~5)		5
D	해당 연도의 몇 번째 일(1~366)		364
d	해당 월의 몇 번째 일(1~31)		30
F	해당 월의 몇 번째 요일(1~5)		5
E	요일(월~일)				Sat
a	오전/오후(AM, PM)			PM
H	시간(0~23)				21
h	시간(1~12)				9
K	시간(0~11)				9
k	시간(1~24)				21
m	분(0~59)				31
s	초(0~59)				8
S	1/1000초(0~999)				297
Z	타임존					+0900
z	타임존(RFC 822)				KST
```


