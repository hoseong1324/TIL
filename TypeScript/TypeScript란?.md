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

이와 같이 타입을 명시함으로 인해 확실한 오류 확인이 가능하다.
