### React-Router V6 변경된 것들

- switch -> routes 네이밍 변경
```
// v5
<Switch>
  <Route ... />
</Routes>

// v6
<Routes>
  <Route ... />
</Routes>
```
- StaticRouter 의 import 위치 변경
```
// v5
import { StaticRouter } from 'react-router-dom';
// v6
import { StaticRouter } from 'react-router-dom/server';
```
- exact 옵션 삭제
ex)
```
// categores 로 시작되는 모든 라우팅 매칭
<Route path='categories/*' />
```
- route 에서 컴포넌트 렌더링
```
import UserInfo from './UserInfo'; // 

// v5 버전 사용 예시
<Route path='user' component={UserInfo} />
<Route
  path='user'
  render={routeProps => (
    <UserInfo routeProps={routeProps} isLogin={true} />
  )}
/>

// v6 버전 사용 예시
<Route path='user' element={<UserInfo />} />
<Route path='user' element={<UserInfo isLogin={true} />} />
```
- 간편해진 중첩 라우팅
#### v5
```
import {
  BrowserRouter,
  Switch,
  Route,
  Link,
  useRouteMatch
} from 'react-router-dom';

function App() {
  return (
    <BrowserRouter>
      <Switch>
        <Route path="/user" component={User} />
      </Switch>
    </BrowserRouter>
  );
}

function User() {

  const { path } = useRouteMatch();
  return (
    <div>
      <Switch>
        <Route path={`${path}/detail`}>
          <UserDetail />
        </Route>
      </Switch>
    </div>
  );
}
```
#### v6
```
import {
  BrowserRouter,
  Routes,
  Route,
  Outlet
} from 'react-router-dom';

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path='user' element={<User />} >
          <Route path='detail' element={<UserDetail />} />
        </Route>
      </Routes>
    </BrowserRouter>
  );
}

function User() {
  return (
    <>
      <Outlet />
    </>
  )
}
```
- useHistory 훅 변경 -> useNavigate
```
// v5
const history = useHistory();

history.push('/home');
history.replace('/home');

// v6
const navigate = useNavigate();

navigate('/home');
navigate('/home', {replace: true});

// v6 에서의 앞으로, 뒤로 가기 사용방법 변화 
<button onClick={() => navigate(-2)}>Go 2 pages back</button>
<button onClick={() => navigate(-1)}>Go back</button>
<button onClick={() => navigate(1)}>Go forward</button>
<button onClick={() => navigate(2)}>Go 2 pages forward</button>
```
- react-router-config 대신 useRoutes 를 사용
```
function App() {
  const element = useRoutes([
    // These are the same as the props you provide to <Route>
    { path: '/', element: <Home /> },
    { path: 'dashboard', element: <Dashboard /> },
    { path: 'invoices',
      element: <Invoices />,
      // Nested routes use a children property, which is also
      // the same as <Route>
      children: [
        { path: ':id', element: <Invoice /> },
        { path: 'sent', element: <SentInvoices /> }
      ]
    },
    // Not found routes work as you'd expect
    { path: '*', element: <NotFound /> }
  ]);

  // The returned element will render the entire element
  // hierarchy with all the appropriate context it needs
  return element;
}
```
