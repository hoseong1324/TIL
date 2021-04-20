### This

인수 명과 필드에 선언되어 있는 매개변수의 명이 같을 때    

확실하게 구분해주기 위하여 this 를 사용함    

this를 사용하면 메소드안의 변수 값이 아닌 필드에 선언되어 있는 변수를 뜻함.    

ex)

```
class ex{
String test = "필드";
public void method(String test){
System.out.println(test);
// 출력값 = method 메소드로 받은 test 의 값
System.out.println(this.test);
// 출력값 = "필드";
  }
}
```
#### 단 ! Static인 메소드에서는 this가 사용 불가하다    

Static 메소드 내에서 this 를 사용하고 싶으면 객체를 따로 생성 후 사용해야 한다.    



### Final 

Final로 정의된 변수는 변경할 수 없다.    

생성자, 메소드에도 사용이 가능하며 final로 생성자 또는 메소드를 만들경우 재정의(Override) 가 불가하다.
