### Ext.js
```
Ext.onReady(function){
  Ext.create("Ext.containor.Viewport", {
    renderTo : Ext.getBody(),     // 어떤 태그에 뿌릴 것인지(보여질 것인지) 
                                  // 특정 태그안에 삽입하고 싶다면 DOM을 사용해 document.getElementById("id") 와 같이 사용할 수도 있다.
    border : true,
    layout : 'fit',               // 반응형(fit)
    items : [{                    // Json arry 형태
      xtype : 'textfield'         // 아래의 Ext.create 와 같고 input type="" 와 비슷하다고 보면 됨
      },{
      xtype : Ext.create("Ext.form.field.Text")
      }]
   });
});
```

### layout
layout은 region 으로 설정한다 .     
속성 - north, center, south, east, west


### 예제로 보기
```
{
  xtype : 'textfield',
  fieldLabel : '_^_라벨이름',       // 입력요소 앞에 붙는 라벨
  itemId : 'testNm',               // ExtJS상에서 해당구성요소를 정의하는 고유의 이름
  name : 'testNm',                 // submit 할 때 서버에 전송되는 data 명
  flex : 1,                        // 컨테이너 크기를 기준으로 해당구성요소가 차지하는 비율
  value : '테스트',                 // 입력창에 노출되는 값
  readOnly : true                  // 읽기전용여부
}

  bind : {                          // bind
    value : '{currentRecord.testNm}',   // viewModel에 정의된 변수에 value를 담아 사용가능
    readonly : '{readonlyConfig}'       // textfield 뿐 아니라 다른 xtype에도 동일하게 적용가능
  }
```
##### 라벨명에 _^_ 표시는 다국어 처리를 위해서임.
