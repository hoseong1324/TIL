```
SELECT * 
FROM TEST
WHERE REGEXP_LIKE(column,' ');
```
컬림에 문자포함여부를 알고싶을 때 사용
Oracle 에서는 %가 아닌 | 로 사용하여 쓴다
