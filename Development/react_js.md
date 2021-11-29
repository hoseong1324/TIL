### 리액트(React.js) 는 jsx 문법을 사용한다.    
#### jsx 란 ?    
 JavaScript eXtension의 약자로 쉽게 말하면 자바스크립트 코드 내에 HTML 문법을 적은 것이다.     
 외관상 HTML같은 마크업 언어를 리터럴로 입력하는 것으로 보이는데, 빌드 시 Babel에 의해 자바스크립트로 변환된다    
#### Babel 이란 ?
자바스크립트 컴파일러 라고 생각하면 됨.
 
#### jsx 를 사용할 때 주의할 점
- HTML요소에 Class 명을 정의할 때,  원래 HTML에서는 <p class="containor"></p>와 같이 하면 되지만,      
Class라는 단어가 EMCAScript6(ES6)의 클래서 문법과 겹치는 예약어이므로 className이라는 단어를 사용한다      
- 마찬가지로 루프문 예약어와 겹치는 for문은 htmlFor로 사용한다.
- 요소에서 이벤트를 핸들링하는 onclick등의 단어들은 onClick처럼 카멜표기법으로 작성해야함.
- 기존 HTML 주석은 `<!-- 주석 -->` 이렇게 하지만 JSX에서는 `{/* 주석 */}` 으로 표현한다.
- HTML Custom-Element 는 <my-element> 와 표기하였지만, React에서는 <MyElement/> 와 같이 Pascal Case로 표기한다.  닫는 태그에는 꼭 명시적으로 /> 표기를 해준다.
- JSX 내에서 javascript 의 값을 사용할 때에는 {}로 불러옴.      
 ex )
 ```
   const testText = "테스트" 
   <div>이 영역은 {testText} 입니다<div/>
  
 Output -->   이 영역은 테스트 입니다
 ```   
 와 같은 식이다
