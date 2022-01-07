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
