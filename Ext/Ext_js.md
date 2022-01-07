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


### 속정정리
```
-- 텍스트폼
  xtype 
  fieldLabel       // 입력요소 앞에 붙는 라벨
  itemId           // ExtJS상에서 해당구성요소를 정의하는 고유의 이름
  name             // submit 할 때 서버에 전송되는 data 명
  flex             // 컨테이너 크기를 기준으로 해당구성요소가 차지하는 비율
  value            // 입력창에 노출되는 값
  readOnly         // 읽기전용여부
  -- 날짜 폼
  editable         // 입력창에 값을 직접 입력 가능 여부 설정
  -- 콤보박스 폼
  displayField     // 함목에 노출되는 값
  valueField       // 항목을 선택시 서버에 전송되는 값
  queryMode        // 해당 combobox가 ''의 data를 로드하도록 함
  -- 숫자입력 폼
  hideTrigger         // 입력박스 안에 수량을 장가감소 시키는 버튼을 노출할지 여부
  keyNavEnabled       // 화살표 키로 수량을 증가감소 시킬 수 있는지 여부
  mouseWheelEnabled   // 마우스 휠로 수량을 증가감소 시킬 수 있는지 여부
  allowBlank          // 포커스 아웃될 때 입력값이 없어도 될 지 여부
  allowOnlyWhitespace // 스페이스바 빈칸 입력가능 여부
  enableKeyEvents     // 키 이벤트 여부
  validataOnChange    // 값이 변경될 때마다 유효성 체크여부
  validateOnBlue    // 포커스 아웃될 때 유효성 체크여부
  
  bind : {                          // bind
    value : '{currentRecord.testNm}',   // viewModel에 정의된 변수에 value를 담아 사용가능
    readonly : '{readonlyConfig}'       // textfield 뿐 아니라 다른 xtype에도 동일하게 적용가능
  }
```
##### 라벨명에 _^_ 표시는 다국어 처리를 위해서임.

