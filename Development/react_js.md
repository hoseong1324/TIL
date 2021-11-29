### 리액트(React.js) 는 jsx 문법을 사용한다.    
#### jsx 란 ?    
 JavaScript eXtension의 약자로 쉽게 말하면 자바스크립트 코드 내에 HTML 문법을 적은 것이다.     
 외관상 HTML같은 마크업 언어를 리터럴로 입력하는 것으로 보이는데, 빌드 시 Babel에 의해 자바스크립트로 변환된다    
#### jsx 를 사용할 때 주의할 점
- HTML요소에 Class 명을 정의할 때,  원래 HTML에서는 <p class="containor"></p>와 같이 하면 되지만,      
Class라는 단어가 EMCAScript6(ES6)의 클래서 문법과 겹치는 예약어이므로 className이라는 단어를 사용한다      
- 마찬가지로 루프문 예약어와 겹치는 for문은 htmlFor로 사용한다.
