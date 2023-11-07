### 웹서버 올리기

1. web서버 설치<br/>
  <code>apt-get install nginx</code> 명령어를 사용해 nginx를 설치하면 /var/www/html 이라는 디렉토리가 생성된다.
<br/>
2. 파일 업로드
   winscp 프로그램을 이용해서 window에서 서버로 사진을 하나 옮긴다.  
   혹은 wget http://www.google…… 라는 wget 명령어를 사용해 사진을 사이트에서 다운받는다.
<br/>
3. index.html 생성
   <code>vi /var/www/html/index.html</code>를 입력하여 index.html을 생성 및 편집한다. 해당 파일 안에는 다음과 같은 내용이 들어간다. 
   ```<img src=”./이미지이름”>```
<br/>
4. 서버의 ip주소로 접속하면 올린 사진을 확인할 수 있다. 
