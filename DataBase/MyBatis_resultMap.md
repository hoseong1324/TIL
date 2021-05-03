#### ORM 작성 전 result Map 을 선언하여 지정한 컬럼명을 사용자가 지정하는 네임으로 바꾸어서 사용할 수 있다.      
```
<resultMap id="test" type="com.test.spring.dto.testDTO">
    <result property="test1"  colume="DBcolumn1">
    <result property="test2"  colume="DBcolumn2">
    <result property="test3"  colume="DBcolumn3">
 </resultMap>
      
  <select id="testselect" parameterTyle="com.test.spring.dto.testDTO"resultMap="test">
  select * 
  from test
  </select>
  ```
 #### 간단 정리
