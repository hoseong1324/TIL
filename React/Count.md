``` 
const [count, setCount] =useState(0);
function countChk(){
  alert("현재 카운트는 " + count + "입니다");
}
useEffect (() => {
  document.title = `카운팅 ${count} `;
})

return (
       <button onClick={()=> setCount(count+1)}>카운트증가</button>
        <button onClick={()=> setCount(count-1)}>카운트감소</button>
        <button onClick={countChk}>현재 카운트 팝업</button>
        )
```        
카운트 증가 React Hook 
