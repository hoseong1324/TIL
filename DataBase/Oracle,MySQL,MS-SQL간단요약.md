```
/// 1. 공백치환 함수 

Oracle : SELECT NVL('컬럼명', '') FROM DUAL;
MySql : SELECT IFNULL('컬럼명', '') FROM DUAL;
MS-SQL : SELECT ISNULL('컬럼명', '') FROM DUAL;

/// 2. 현재 날짜시간

Oracle : SYSDATE
Mysql  : NOW() 

/// 3. 날짜포멧 

Oracle : TO_CHAR(sysdate,'MMDDYYYYHH24MISS')
Mysql  : DATE_FORMAT(now(),'%Y%m%d%H%i%s')  -> 여기서 대문자Y는 4자리 년도, 소문자 y는 2자리 년도

/// 4. 날짜 포멧 : 요일

Oracle : 요일이 1~7로 인식함  -> TO_CHAR(SYSDATE - 1, 'D') 
Mysql : 요일이 0~6으로 인식   -> DATE_FORMAT(DATE_SUB(NOW(), INTERVAL 1 DAY), '%w')

* 참고로 자바스크립트가 0~6으로 인식하기에 Oracle 쿼리에서 -1을 해서 맞추는 경우가 많음

/// 5. Like절 '%' 사용법
Oracle : Like '%'||'문자'||'%' 이런식으로 컬럼명 앞뒤로 '%'를 붙여주면 된다
Mysql : LIKE CONCAT('문자','%') 이런식으로 CONCAT 함수 사용

/// 6. 형변환
Oracle : To_char, To_number 등
Mysql : CAST
SELECT TO_CHAR(1234) FROM DUAL 
-> SELECT CAST(1234 AS CHAR) FROM DUAL

/// 7. 대소문자 구분함
Oracle : 구분없음
Mysql : 기본적으로 구분하나, 설정으로 변경 가능함

/// 8. ROWNUM
Oracle : where 절에 rownum > 5 and rownum =< 10 
Mysql : where절 없이 limit 5,10

/// 9. Sequence(시퀀스)는 둘 다 사용자함수를 만들어서 아래와 같이 사용

Oracle : 시퀀스명.nextval
Mysql : 시퀀스명.currval

/// 10. 문자열 자르기

Oracle: SUBSTR(문자열, 1, 10)
Mysql: SUBSTRING(문자열, 1,10), LEFT(문자열, 3), RIGHT(문자열, 3)

/// 11. 문자열 합치기 ( - 문자열을 연결한다고 가정)

Oracle: 문자열(또는 컬럼) ||' - '
Mysql: CONCAT(문자열(또는 컬럼), ' - ')

/// 12. 예약어가 컬럼명일 때

Oracle: 컬럼명을 따옴표(")로 감싸기 (예: select "column" from tab)
Mysql: 컬럼명을 TAB 키 위에 있는 ` 키 ( Single quotation )로 감싸기


/// 13. 저장프로시저 있는지 여부 파악해서 Create 하기

Oracle: CREATE OR REPLACE PROCEDURE 프로시저명
Mysql: DROP PROCEDURE IF EXISTS 프로시저명; 을 한 뒤에 CREATE PROCEDURE 프로시저명
```
