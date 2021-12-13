### Hook 이란 React 16.8버전 부터 적용가능한 클래스컴포넌트에서 사용하던 것들을 함수 컴포넌트에서 사용할 수 있게 해주는 것이다.

⚡️ State Hook       
{useState}     
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


⚡️ Effect Hook     
{useEffect}    
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
