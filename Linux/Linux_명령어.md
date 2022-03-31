##### ls - 현재 위치의 파일목록을 조회하는 명령어     
##### cd - 디렉토리를 이동하는 명령어     
##### touch - 파일의 용량이 0인 파일을 생성, 날짜 변경하는 명령어     
##### mkdir - 디렉토리를 생성하는 명령어     
##### cp - 파일을 복사하는 명령어     
##### mv - 파일을 이동시키는 명령어     
##### rm - 파일을 제거하는 명령어     
##### cat - 파일의 내용을 화면에 출력하거나 파일을 만드는 명령어     
##### redirection - 화면에 출력되는 결과를 파일로 저장하는 명령어     
##### alias - 자주 수행하는 명령어들을 쉽게 사용할 수 있도록 설정하는 명령어     




https://gomguard.tistory.com/73 추가 예정
```
cd - 위치 이동

pwd - 현위치 위치

mkdir 폴더이름 - 폴더생성

vi 파일이름 - 파일 생성, 파일 편집

q! - 강제종료, wq - 저장하고 종료
cp [원본] [사본] - 복사

mv [원본] [옮길위치] - 파일 이동

ll - 현위치 파일 리스트

history - 명령어 기록

netstat -nltp - 네트워크 확인(포트)

grep - 글자 찾기

ex) ps -ef | grep tomcat
rpm -Uvh [rpm] - 패키지 설치

tar -xvzf [파일] [경로] - tar 파일 압축 해제

make

configure - 컴파일
make - 소스파일 컴파일 > binary 파일 만듬
make install - binary 파일 지정된 경로로 이동
find - 파일 찾기

ex) find / -name # - 파일명에 #이 포함된 파일 찾음
chown [소유자:그룹] [파일] - 파일 소유자, 그룹 설정

ps -ef - 실행중인 프로세스 목록

kill

kill [PID] - 프로세스 종료
kill -9 [PID] - 프로세스 강제 종료
top - cpu, memory 사용량 모니터링

df -h - 디스크 용량

ssh [계정]@[ip] - ssh 접속
```
### Web 서버 구축
```
yum 가능
yum install httpd => /etc/httpd/ 경로로 다운로드 됨

tomcat과 연동

mod_jk 설치
mod_jk 설치에 필요한 컴파일러와 필요한 라이브러리 설치 yum install gcc gcc-c++ httpd-devel wget -c #링크 tar zxvf tomcat-connector-# ./configure --with-apxs=/etc/httpd/bin/apxs make && make install
httpd Modules > mod_jk.so 파일 확인

workers.properties 파일 설정 worker.list=worker1 worker.worker1.port=8009 worker.worker1.host=localhost worker.worker1.type=ajp13 #worker.worker1.secret=[your secret key]

httpd.conf에 include, 모듈 설정 include conf/mod_jk.conf

LoadModule jk_module modules/mod_jk.so

JkWorkersFile conf/workers.properties JkLogFile logs/mod_jk.log JkLogLevel info #JkMountFile conf/uri.properties
vhosts 설정 부분에 JkMount /* worker1

yum 불가능
apr, apr-util, expat, httpd, openssl, pcre, tomcat-connectors, zlib 각 의존 버전에 맞는 버전 필요

ex) * /home/Apache 디렉토리 설치 기준

https://httpd.apache.org 에서 apache 웹서버를 다운로드

tar xvfz httpd-2.4.43.tar.gz 로 압축 해제

http://apr.apache.org 에서 apr 다운로드 후 설치

1.7.0 버전 다운로드
/home/Apache 폴더에 이동시켜놓음
tar xvfz apr-1.7.0
cd apr-1.7.0
./configure --prefix=/home/Apache/apr1.7.0
make && make install
http://apr.apache.org 에서 apr-util 다운로드 후 설치
1.6.1 버전 다운로드
/home/Apache 폴더에 이동시킴
tar xvfz apr-util-1.6.1.tar.gz
cd apr-util-1.6.1
./configure --prefix=/home/Apache/apr-util1.6.1 --with-apr=/home/Apache/apr1.7.0 (open ssl 이 설치 되는 거면 --with-openssl=경로 옵션을 추가해 줘야 할 것으로 보임)
make && make install
make 시 에러가 발생함 xml/apr_xml.c:35:19: fatal error: expat.h: 그런 파일이나 디렉터리가 없습니다

expat-devel 설치 https://libexpat.github.io 에서 다운로드 받음 expat2.2.9 버전 다운로드 받음 /home/Apache 에 expat-2.2.9.tar.gz 이동 tar xvfz expat-2.2.9.tar.gz ./configure --prefix=/home/Apache/expat2.2.9 make && make install

다시 /home/Apache/apr-util-1.6.1 폴더 이동 ./configure --prefix=/home/Apache/apr-util1.6.1 --with-apr=/home/Apache/apr1.7.0 --with-expat=/home/Apache/expat2.2.9

make && make insatll

pcre 설치
https://www.pcre.org 에서 다운로드 받음 pcre-8.42.tar.gz 로 다운 받았음
/home/Apache 폴더에 복사함
tar xvfz pcre-8.42.tar.gz
cd pcre-8.42
./configure --enable-utf8 --prefix=/home/Apache/pcre8.42
make && make install
openssl 설치
https://www.openssl.org 에서 다운로드 받음
openssl-1.1.1g.tar.gz 를 받음
/app 폴더로 이동
tar xvfz openssl-1.1.1g.tar.gz
cd openssl-1.1.1g
./config --prefix=/home/Apache/openssl1.1.1g --openssldir=/home/Apache/openssl1.1.1g shared
make && make install
./config 명령어에서 안되면 linux-x86-64 제거 (이미 선언되어있다는 오류 발생 시)

다시 apache 설치로 돌아감
cd /home/Apache/httpd-2.4.43
./configure --prefix=/home/Apache/apache2.4.43 --enable-mods-shared=all --enable-so --enable-rewrite --enable-proxy --enable-proxy-ajp --enable-proxy-balancer --enable-proxy-http --enable-proxy-connect --enable-ssl --with-apr=/home/Apache/apr1.7.0 --with-apr-util=/home/Apache/apr-util1.6.1 --with-pcre=/home/Apache/pcre8.42 --with-ssl=/home/Apache/openssl1.1.1g
(동시접속자가 많은 사이트의 경우 --with-mpm=worker 추가)

make && make install
apache , tomcat 연동 -tomcat connector 설치 -tar xvfz tomcat-connectors-1.2.48-src.tar.gz -cd /home/Apache/tomcat-connectors-1.2.48-src/native -./configure --with-apxs=/home/Apache/apache2.4.43/bin/apxs -(apxs 옵션값은 아파치 설치 디렉토리/bin/apxs 을 지정한다.) -make && make install
httpd service 등록
서비스 파일 생성 $ vi /usr/lib/systemd/system/apache.service

[Unit] Description=apache After=network.target syslog.target

[Service] Type=forking User=root Group=root

ExecStart=/etc/httpd/bin/apachectl start ExecStop=/etc/httpd/bin/apachectl stop

Umask=007 RestartSec=10 Restart=always

[Install] WantedBy=multi-user.target

systemctl daemon 재시작 $ systemctl daemon-reload

정상적으로 Service가 등록되었는지 확인 $ systemctl status apache

서비스 자동 시작 $ systemctl enable apache
```
