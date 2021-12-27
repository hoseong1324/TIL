### react-router


npm i react-router-dom      
react-router 는 react-router-dom 을 설치하면 같이 설치가 된다.    
`import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';`    

임포트 하고  
```
<Router>
        <Routes>
        <Route path='/'  element={<SignPage/>} />
        <Route path='/main' element={<MainPage/>} />
        <Route path='/profile' element={<ProfilePage/>} />
        </Routes>
      </Router>
```
이런 식으로 사용

### exact 와 Switch 는 router-dom v6 부터 사용하지 않는다!!     
- 변경전
```
<Router>
        <Switch>
        <Route path='/'exact  component={SignPage} />
        <Route path='/main' component={MainPage} />
        <Route path='/profile' component={ProfilePage} />
        </Switch>
      </Router>
```
- 변경후
```
<Router>
        <Routes>
        <Route path='/'  element={<SignPage/>} />
        <Route path='/main' element={<MainPage/>} />
        <Route path='/profile' element={<ProfilePage/>} />
        </Routes>
      </Router>
```
 
### 404 Page     
`<Route path='*' element= {<div className="error">에러페이지</div>}/>`     
위처럼 하거나 404Page 컴포넌트를 만들어서 노출시켜준다.     

