### TypeScript란 ?
- 동적 타입 언어인 JavaScript 의 타입안정성을 보완하기위해 나온 정적 타입 언어이다.
- JavaScript 에 타입을 추가한 언어 ( 자바스크립트의 확장 언어 ) 


JavaScript 와의 차이 
### ex
#### JavaScript
```
function test(a + b){
return a+b;
}

/// input test(10,20)
/// output  30

/// input test('10','20')
/// output 1020
```
#### TypeScript
```
function test(a : number, b: number){
return a+b;
}

/// input test(10,20)    
/// output  30     

/// input test('10','20')      
/// output Error : TS2345 Argument of type '"10"' is not assignable to parameter of type 'number'.
```

이처럼 TypeScript는 정적 타입을 지원하므로 컴파일 단계에서 오류를 포착할 수 있는 장점이 있습니다.      
명시적인 정적 타입 지정은 개발자의 의도를 명확하게 코드로 기술할 수 있고 이는 코드의 가독성을 높이고 예측할 수 있게 하며 디버깅을 쉽게한다.
