### UNION 

> select num,name from test  
>
> union    
>
> select number as num, title as name from test2    



union을 사용할 때에는 조회하는 두 테이블의 컬럼 수, 컬럼 명이 같아야하며, 컬럼명이 다를 시 as 를 통하여 바꾼 후 조회한다.



union은 중복된 값을 제외하고 조회하며, union all 은 중복값도 포함하여 조회한다.
