# Oracle Hint
## 사용법 
`/*+ INDEX(a EMP_IDX02) */`     
INDEX = 인덱스 힌트      
a = 테이블 명     
EPM_IDX02 = 인덱스 명     

####  `/*+ [힌트] */ ` (멀티라인 주석)
####  `--+ [힌트] ` (싱글라인 주석)       

### 정리
- order by 를 사용하지 않아도 인덱스의 컬럼 순서대로 정렬되어 조회됨
- 여러개의 인덱스 힌트 사용가능(`/*+ index(...) index(...) */`)
  - 여러개를 사용할 때 콤마(,)가 아닌 스페이스바(공백)으로 구분하여 사용
- INDEX : 오름차순 정렬 (Default INDEX_ASC)
- INDEX_DESC : 내림차순 정렬


1. 최적화 목표
```
- /*+ALL_LOWS */: 전체 처리속도 최적화

-/*+FIRST_ROWS(N) */ : 최초 N건 응답속도 최적화
```
 

 

 

2.액세스 방식
```
- /*+FULL */ :인덱스 타지말고 바로 테이블 풀스캔으로 접근해라

- /*+INDEX */: 인덱스를 타라

- /*+INDEX_DESC */: 인덱스를 ORDER BY DESC 역순으로 타라 (시간, 결과값등 최근인것 혹은 MAX값 구할때 좋음)

- /*+INDEX_FFS */: INDEX FAST FULL SCAN으로 타라

- /*+INDEX_SS */: INDEX SKIP SCAN
```
 

 

 

3. 조인순서
```
- /*+ORDERED */: FROM절에 나열된 테이블 순서대로 조인해라

- /*+LEADING */: 내가 힌트절에 열거한 테이블 순서대로 조인해라 EX: /*+ LEADING (A B C)*/

                       -- A,B,C 순서대로 조인하세요

- /*+SWAP_JOIN_INPUTS */: 해시조인의 경우, BUILD INPUT를 명시적으로 선택

                              EX: /*+ SWAP_JOIN_INPUTS(A)*/

                              --해시조인의경우 BUILD INPUT과 PROBE에 대한 순서를 정할 수 있다. 
```
 

 

 

4. 조인방식
```
- /*+USE_NL */ :NL(NESTED LOOP - 중첩루프)방식 조인 유도

- /*+USE_MERGE */: 소트머지 조인으로 유도

- /*+USE_HASH */: 해시조인으로 유도

-/*+NL_SJ */: NL SEMI조인으로 유도

-/*+MERGE_SJ */: 소트머지 세미조인으로 유도

-/*+HASH_SJ */: 해시 세미조인으로 유도
```
 

 

 

5. 서브쿼리팩토링
```
- /*+MATERIALIZE */: WITH문으로 정의한 집합을 물리적으로 생성하도록 유도 

EX) WITH /*+ MATERIALIZE*/ T AS (SELECT ...)

- /*+INLINE */: WITH문으로 정의한 집합을 물리적으로 생성하지않고 INLINE 처리하도록 유도

EX)WITH /*+ INLINE*/ T AS (SELECT ...)
```
 

 

 

6.쿼리변환
```
- /*+ MEERGE */: 뷰 머징 유도

- /*+NO_MERGE */: 뷰 머징 방지

- /*+UNNEST */: 서브쿼리 UNNESTING 유도

- /*+NO_UNNEST */: 서브쿼리 UNNESTING 방지

- /*+PUSH_PRED */: 조인조건 PUSHDOWN 유도

- /*+NO_PUSH_PRED */: 조인조건 PUSHDOWN 방지

- /*+USE_CONCAT */: OR 또는 IN-LIST조건을 OR-EXPANSION으로 유도

- /*+NO_EXPAND */: OR 또는 IN-LIST 조건에 대한 OR-EXPANSION방지
```
 

 

 

7.병렬처리
```
- /*+PARALLEL */: 테이블 스캔,  DML 병렬방식으로 처리하도록 할때 사용.. 단일 대형 테이블의 접근시 정말 많이 쓴다.

                EX) /*+ PARALLEL(T1 4)*/

- /*+PARALLEL_INDEX */: 인덱스 스캔을 병렬방식으로 처리하도록 유도

- /*+PQ_DISTRIBUTE */: 병렬수행시 데이터 분배방식 결정

                        EX) PQ_DISTRIBUTE(T1 HASH(--BUILD INPUT) HASH(--PROBE TABLE))

 ```

 

 

 

8. 그외 기타
```
- /*+APPEND*/: DIRECT PATH INSERT유도로  INSERT  문에 주로 많이 쓴다

- /*+DRIVING_SITE */: DB LINK REMOTE쿼리에 대한 최적화 및 실행 주체 지정 (LOCAL 또는  REMOTE)

- /*+PUSH_SUBQ */: 서브쿼리를 가급적 빨리 필터링하도록 유도

- /*+NO_PUSH_SUBQ */: 서브쿼리를 가급적 늦게 필터링 하도록 유도 
```

