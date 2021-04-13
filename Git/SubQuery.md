```
Subquery

2021년 3월 17일 수요일
오후 12:00

https://mozi.tistory.com/233

서브쿼리가 단일 행 비교 연산자(=, <, <=, >, >=, <>)와 함께 사용할 때는 서브쿼리의 결과 건수가 반드시 1건 이하여야 합니다.
만약 결과가 2건 이상인 경우 오류가 발생합니다.

서브쿼리가 사용 가능한 곳
1. SELECT 절
2. FROM 절
3. WHERE 절
4. HAVING 절
5. ORDER BY 절
6. INSERT 문의 VALUES 절
7. UPDATE 문의 SET 절

서브쿼리의 결과가 2건 이상 반환될 수 있다면 반드시 다중 행 비교 연산자(IN, ALL, ANY, SOME)와 함께 사용해야 합니다.



다중행 서브쿼리 
	- 수행결과 여러개를 반환    
( https://m.blog.naver.com/PostView.nhn?blogId=leeminji25&logNo=220909398272&proxyReferer=https:%2F%2Fwww.google.com%2F )
```
