[참조](https://dev-pengun.tistory.com/entry/React-%EB%A6%AC%EC%95%A1%ED%8A%B8-%EA%B8%B0%EC%B4%88-%EB%B0%B0%EC%9A%B0%EA%B8%B0-4-State-%EC%99%80-%EC%83%9D%EB%AA%85%EC%A3%BC%EA%B8%B0?category=913270)      
[참조2- 이게 더 좋은 듯](https://velog.io/@somangoi/TIL042-React-Session-2-Router)
### 리액트(React.js) 는 jsx 문법을 사용한다.    
#### jsx 란 ?    
 JavaScript eXtension의 약자로 쉽게 말하면 자바스크립트 코드 내에 HTML 문법을 적은 것이다.     
 외관상 HTML같은 마크업 언어를 리터럴로 입력하는 것으로 보이는데, 빌드 시 Babel에 의해 자바스크립트로 변환된다    
#### Babel 이란 ?
자바스크립트 컴파일러 라고 생각하면 됨.
 
#### jsx 를 사용할 때 주의할 점
- HTML요소에 Class 명을 정의할 때,  원래 HTML에서는 `<p class="containor"></p>`와 같이 하면 되지만,      
Class라는 단어가 EMCAScript6(ES6)의 클래서 문법과 겹치는 예약어이므로 className이라는 단어를 사용한다      
- 마찬가지로 루프문 예약어와 겹치는 for문은 htmlFor로 사용한다.
- 요소에서 이벤트를 핸들링하는 onclick등의 단어들은 onClick처럼 카멜표기법으로 작성해야함.
- 기존 HTML 주석은 `<!-- 주석 -->` 이렇게 하지만 JSX에서는 `{/* 주석 */}` 으로 표현한다.
- HTML Custom-Element 는 `<my-element>` 와 표기하였지만, React에서는` <MyElement/>` 와 같이 Pascal Case로 표기한다.  닫는 태그에는 꼭 명시적으로 /> 표기를 해준다.
- JSX 내에서 javascript 의 값을 사용할 때에는 {}로 불러옴.      
 ex )
 ```
   const testText = "테스트" 
   <div>이 영역은 {testText} 입니다<div/>
  
 Output -->   이 영역은 테스트 입니다
 ```   
 와 같은 식이다


### React 시작
cmd창을 열어 리액트를 사용하기  프로젝트를 생성한다
```
npm install (-g) create-react-app
create-react-app 프로젝트이름
```
프로젝트 폴더로 이동한 후                 
npm start 로 시작한다           
난 VScode 사용             
에디터 이용하여 생성한 폴더 오픈 후 src-App.js 파일에서 수정하여 localhost:3000 에 변경되는지 확인( 저장 시 바로 변경 )


### 컴포넌트 사용
```
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```
위의 함수는 엘리먼트를 return 하기때문에 컴포넌트이고, 함수로 정의되었기 때문에 함수 컴포넌트라고 한다.
```
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```
위는 클래스로 정의하는 방법이다.
#### 컴포넌트는 항상 대문자로 시작되어야 한다.

### props 사용하기
```
function PropsTest(props){
  return <div>"this " + {props.name}</div>
  }
  
function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
               <Proro name = {'react'}/>
               <Proro name = {'test'}/>
               <Proro name = {'what'}/>
          </header>
    </div>
              )
         }
```
위 처럼 컴포넌트에 프로퍼티로 전달 된 것들은 props.name 으로 가져올 수 있다.        
props를 활용할 때 div 안에 묶여있는 것은 묶인 값으로 꺼내어 재사용 할 수 있도록 사용하는 것이 좋다     
props는 읽기전용이므로 수정하려고 하면 에러가 발생한다      

### State 사용하기

```
    constructor(props) {
        super(props);
        this.state = {
            date : new Date()
        };
    }
```
date라는 state를 만들었고, 초기값은 생성된 당시의 시간을 담고있는 date객체임
이제 this.state.date로 date에 접근할 수 있다.      
`this.state.date.toLocaleTimeString()`    
 date에는 date객체가 들어가 있기 때문에 date객체 내장 함수인 toLocaleTimeString을 불러 현재 시간을 가져올 수 있다.
### 클래스 컴포넌트 사용하기
`import React, {extends 명} from "react";`        
다 작성한 후 가장 밑에        
`export default Class명;`      
App.js 파일에       
`import Class명 from '위치';`


### 이벤트 핸들링 사용하기
React 는 카멜표기법을 사용하며        
`onclikc=함수()` 가 아닌 `onClick={함수}` 를 사용한다     

event를 인자로 받고, e.preventDefault()를 호출하면, 이벤트의 기본동작은 동작하지 않게 되고 console.log만 된다     

이벤트 핸들링에 인자를 전달하는 방법은 두가지가 있다         
=> 화살표를 사용하는 방법       
`<button onClick= { () => Click("msg") }> click! </button>`     
bind() 를 사용하는 방법             
`<button onClick ={ Click.bind(자료형,"msg") }> click! </button>`     


### 조건부 랜더링
```
function Login(){
  return (
    <button>로그인</button>
  );
}
function Logout(){
  return (
    <button>로그아웃</button>
  );
}
function UserButton(props){
  if(props.isLoggenIn){
    return <Logout/>;
  }
  return <Login/>;
}
```
세가지의 함수를 만들고,      
`<UserButton isLoggenIn={false}></UserButton>`     
함수를 통하여 조건에 따라 다른 리턴값으로 버튼을 표출한다.
{} 안에 jsx 를 사용하여 ?: 와 같이 삼항연산자를 사용 할 수도 있고  && 연산자 등을 통해 if의 조건으로도 사용 가능하다.     


### 컴포넌트 랜더링 막기 
```
function WarningBanner(props){
  if(!props.warn){
    return null;
  }
  return(
    <div className="warning">
      Warning!!!
    </div>
  );
}
```
특정 상황에만 렌더링 되어야 하는 컴포넌트는 return null을 이용해 렌더링 되지 않게 할 수 있다.
