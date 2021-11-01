```
MySql - Date_format()
Oracle - To_char()

Datetime = 
%k = 24시간제 < mysql >
HH24 = 24시간제 < oracle >


--날짜 포맷
TO_CHAR(SYSDATE,'YYYYMMDD'),--20200607 
TO_CHAR(SYSDATE,'YYYY-MM-DD'),--2020-06-07
TO_CHAR(SYSDATE,'YYYY/MM/DD'),--2020/06/07
TO_CHAR(SYSDATE,'YYYY'),--2020 TO_CHAR(SYSDATE,'YY'),--20
TO_CHAR(SYSDATE,'MM'),--06
TO_CHAR(SYSDATE,'MON'),--JUN TO_CHAR(SYSDATE,'D'),--1 (주중의 일을 1~7로 표시(일요일 = 1) TO_CHAR(SYSDATE,'DD'),--07 
TO_CHAR(SYSDATE,'DDD'),--159 (1년기준 일 수) 
TO_CHAR(SYSDATE,'DAY'),--SUNDAY (요일 표시) 
TO_CHAR(SYSDATE,'DY'), --SUN (요일을 한자리로 표시) 
TO_CHAR(SYSDATE,'WW'), -- 23 (일년 기준 주를 00 ~ 53 형태로 표시) 
TO_CHAR(SYSDATE,'W'), -- 1 (한달 기준 몇번째 주) 
TO_CHAR(SYSDATE,'DL'),--Sunday, June 07, 2020 

--시간 포맷 
TO_CHAR(SYSDATE,'AM'),--AM 
TO_CHAR(SYSDATE,'PM'),--AM 
TO_CHAR(SYSDATE,'HH'), --11 (시간을 0 ~ 12 형태로 표시) 
TO_CHAR(SYSDATE,'HH24'), --11 (시간을 0 ~ 24 형태로 표시) 
TO_CHAR(SYSDATE,'MI'), --15 (분을 00 ~ 59 형태로 표시) 
TO_CHAR(SYSDATE,'SS'), --51 (초을 01 ~ 59 형태로 표시) --세기 포맷 
TO_CHAR(SYSDATE,'CC'), --21 (세기) 
TO_CHAR(SYSDATE,'BC') --AD

```
