### Hooks

```
import React, {useState} from "react";
import '../App.css';


const App = () => {
  const [Number, setNumber] = useState(0);
  const [test , setValue] = useState("");

  const onChangeTest = e => {
    console.log("랜더링~");
    setValue(e.target.value);
  }
  return (
    <div>
      <h1>현재값 : {Number}</h1>
        <button onClick ={() => {setNumber(Number+1)}}>증가</button>
        <button onClick = {() => {setNumber(Number-1)}}>감소</button>
      <h1>입력한 내용 : {test}</h1>
        <input name="test" placeholder="입력값" onChange={onChangeTest}/>
    </div>
  )
}

export default App;

```

### App.js 파일 
