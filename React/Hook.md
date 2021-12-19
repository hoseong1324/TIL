### Hook 이란 React 16.8버전 부터 적용가능한 클래스컴포넌트에서 사용하던 것들을 함수 컴포넌트에서 사용할 수 있게 해주는 것이다.

### [Hook API](https://ko.reactjs.org/docs/hooks-reference.html) 

### ⚡️ State Hook       
{useState}     [참조](https://ko.reactjs.org/docs/hooks-state.html)
```
import React, { useState } from 'react';

function Example() {
  const [count, setCount] = useState(0);
  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```
위와 같이 useState를 사용함으로 인해 클래서컴포넌트에서 처럼 이전 state 와 현재 state를 합칠 필요가 없다.      


### ⚡️ Effect Hook     
useEffect를 사용하기위해선 npm install axios 를 해주자    
{useEffect}    [공식문서](https://ko.reactjs.org/docs/hooks-effect.html)        
               [useEffect 참조](https://overreacted.io/ko/a-complete-guide-to-useeffect/)
```
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  // componentDidMount, componentDidUpdate와 비슷합니다
  useEffect(() => {
    // 브라우저 API를 이용해 문서의 타이틀을 업데이트합니다
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```
위와 같이 useEffect 를 사용함으로 인해 클래스컴포넌트에서는 각각 쪼개어 주던 생명주기 메서드를 한군데에 모아서 작성 할 수 있다.    
document.title = 부분에 따옴표, 쌍따옴표 아니고 1옆에 있는 ` 이다 !!!

### ⚡️ Hook 사용규칙
Hook은 그냥 JavaScript 함수이지만, 두 가지 규칙을 준수해야 한다.
 
최상위(at the top level)에서만 Hook을 호출해야 한다.       
반복문, 조건문, 중첩된 함수 내에서 Hook을 실행하지 말 것 !     
React 함수 컴포넌트 내에서만 Hook을 호출해야 한다.      
일반 JavaScript 함수에서는 Hook을 호출해서는 안된다.      
(Hook을 호출할 수 있는 곳이 딱 한 군데 더있는데 직접 작성한 custom Hook 내에서만 가능하다)
