# Index 

## 생성
   `CREATE INDEX [인덱스명] ON [테이블명](컬럼)`
   `CREATE UNIQUE INDEX [인덱스명] ON [테이블명](컬럼)`
   - CREATE 와 INDEX 사이에 UNIQUE를 넣으면 컬럼값에 중복을 허용하지 않는다는 것
## 조회
   `SELECT * FROM user_indexes WHERE table_name = '테이블명'`
## 삭제
   `DROP INDEX [인덱스명]`
## 리빌딩
#### 인덱스 리빌딩 이유
- 인덱스 파일은 C, U, D(insert, updatem delete)를 반복하다보면 성능이 저하됨.
- 인덱스는 트리구조를 가지기 때문에 작업이 오래동안 일어나면 트리 한쪽이 무거워짐으로 인해 트리 깊이가 깊어지기 때문

### 리빌드 대상 조회 쿼리(트리의 깊이가 4이상인 index조회)
```
SELECT I.TABLESPACE_NMAE, I.TABLE_NAME, I.INDEX_NAME, I.BLEVEL,
       DECODE(SIGN(NVL(I.BLEVEL, 99)-3), 1, DECODE(NVL(I.BLEVEL, 99), 99, '?', 'Rebuild'), 'Check') CNF
FROM USER_INDEXES I
WHERE I.BLEVEL > 4
ORDER BY I.BLEVEL DESC;
```
### 리빌드 쿼리
`ALTER INDEX [인덱스명] REBUILD;`
### 전체 인덱스 리빌드 쿼리
`SELECT 'ALTER INDEX ' ||INDEX_NAME|| ' REBUILD' FROM USER_INDEXES;`

## INDEX 사용은 전체 데이터의 10~15% 정도의 데이터가 필요할 때 사용하고, 마지막 사용방법으로 강구하는 것이 좋다 .
## 데이터베이스의 부하를 막기위하여
