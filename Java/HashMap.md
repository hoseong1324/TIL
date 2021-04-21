### HashMap



* HashMap 임포트

`import java.util.HashMap;`

* HashMap 선언

`HashMap<String, Object> map = new HashMap<String, Object>();`

기본적인 선언문이다.          

여기서 HashMap의 속성을 알아보면 HashMap은 저장공간보다 값이 추가로 들어오게 되면 List처럼 저장공간을 추가로 늘리지만 List 처럼 한칸씩 늘리는 것이 아닌 약 두배정도의 크기를 늘리기때문에 선언을 할때 크기를 선언해주는 것이 좋다. 

(선언하지 않는 부분에서 과부하가 많이 발생하기 때문)

* HashMap에 데이터 넣기

 ` map.put("key", "value");`

  put 키워드를 이용하여 앞부분은 key가 되는 이름, 뒷부분은 value가 되는 변수 또는 텍스트를 넣는다.      

* HashMap에서 데이터 꺼내기

  전체를 출력할 때는     

  ` System.out.println(map); `

  `출력값 : { key : value }`

  이렇게 전체를 써주면 되지만 각각의 데이터를 뽑기 위해서는

  `System.out.println(map.get("key"));`

  `출력값 :  value`

  로 키의 이름을 적어서 꺼낸다.

* HashMap에서  데이터 꺼내기 다른 방법

  - Entry 사용
```
  for(map.Entry<String, Object> entry : map.entrySet()){

  System.out.println(entry.getKey() + entry,getValue());

  }
```
  `출력값 : key , value `

  < key와 value 두가지 모두 필요할 때 사용 >

  - keySet() 사용
```
  for( Integer key : map.keySet()){

  System.out.println(keyt , map.get(key));

  }
```
  < key 값만 필요할 때 사용 >

  `출력값 : key , key에 맞는 value`

  - Iterator 사용 ( 전체 데이터 )
```
    Iterator<map.Entry<String, Object> iterator= map.entrySet().iterator();

    while (iterator.hasNext()){

    ​		map.Entry<String, Object> entry = (map.Entry<String, Object>) iteratorE.next();

    ​        String key = entry.getKey();

    ​        String value = entry.getValue();

    ​        System.out.println(key ,  value);

    }
```
  `출력값 : key , value`
```
  ​	 Iterator<String> iterator = map.keySet().iterator();

  ​    while (iterator.hasNext()) {

  ​      String key = iterator.next();

  ​      String value = map.get(key);

  ​      System.out.println(key, value);

  ​    }
 ```
 


  `출력값 : key, value `
### 작성해놓은 자료형은 상황에 따라 바뀐다




