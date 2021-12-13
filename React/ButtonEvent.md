```
import React, {useState} from "react";
import '../App.css';


const App = () => {
  const [Number, setNumber] = useState(0);
  return (
    <div>
      <h1>현재값 : {Number}</h1>
        <button onClick ={() => {setNumber(Number+1)}}>증가</button>
        <button onClick = {() => {setNumber(Number-1)}}>감소</button>
      
    </div>
  )
}
export default App;
```

### App.js 파일 
Number 와 setNumber 를 통해 값 
