### react-router


npm i react-router-dom      
react-router 는 react-router-dom 을 설치하면 같이 설치가 된다.    
`import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';`    

임포트 하고  
```
<Router>
        <Routes>
        <Route path='/'exact  element={<SignPage/>} />
        <Route path='/main' element={<MainPage/>} />
        <Route path='/profile' element={<ProfilePage/>} />
        </Routes>
      </Router>
```
이런 식으로 사용

#### exact?
위와 같이 / 와 /main 처럼 있으면 /와 /main 을 함께 가져오기때문에 정확한 path 를 가져오기 위한 선언.       

#### exact 를 사용하지 않고 매핑하려면 ?
switch 를 사용하면 된다.
```
<Router>
        <Routes>
        <Switch>
        <Route path='/'exact  element={<SignPage/>} />
        <Route path='/main' element={<MainPage/>} />
        <Route path='/profile' element={<ProfilePage/>} />
        </Switch>
        </Routes>
      </Router>
```
#### 주의점    
Switch 를 사용하면 /가 포함된 패쓰중 가장 처음의 경로만 가지고 오기때문에 순서를 잘 지정해주어야 한다.
