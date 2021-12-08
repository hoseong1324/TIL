#### node.js

Node.js 는 서버사이드 자바스크립트이며 구글의 자바스크립트 엔진인 V8을 기반으로 구성된 일종의 소프트웨어 시스템이다.

브라우저에서만 돌아가던 javascript를 외부 응용프로그램으로 빼서    
브라우저 없이 돌아갈 수 있게 자체 엔진이라고 생각하면 됨   

#### 환경변수 Path 설정 필수 !

node.js 는 웹서버를 실행하기 위하여 http 모듈을 require 로 불러옴.
( 다른 언어의 import 와 유사기능 )
workspace 폴더 경로 설정 후 그 폴더에 js 파일 생성후 실행 
cmd 창에서 workspace 로 이동 후 node '파일명' 으로 실행 ( 확장자 x ) 
- http 모듈 설정
`var http = require('http')`
- http 모듈에 내장되어 있는 createServer 함수로 서버 생성
`var server = http.createServer()`
- node.js 는 함수명 없이 function에 선언 된 Parameter 는 이벤트 발생시에 CallBack 된다.
- (생성된 서버로 어떠한 요청이 왔을 시 function 내부의 로직이 실행됨)



https://javafa.gitbooks.io/nodejs_server_basic/content/chapter4.html 공부
