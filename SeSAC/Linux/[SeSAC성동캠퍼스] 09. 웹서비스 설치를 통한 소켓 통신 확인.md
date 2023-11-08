## 웹서비스 설치를 통한 소켓 통신 확인
### | 목적
 테트리스 소스코드를 설치 및 실행하면서 필수 라이브러리를 설치하고, 기타 리눅스 명령어에 익숙해지는 효과를 기대한다.  
 또한, 테트리스를 여러 포트에서 실행 및 접속하면서 현재 실행중인 프로세스를 확인하고 이를 제거하는 동작을 해 보자.  
<br/><br/>

### | 테트리스 설치 및 실행
1. https://www.victornils.net/tetris/ 홈페이지에서 last version을 클릭  
![image](https://github.com/jisoo449/TIL/assets/48276691/13d54bc0-7cfa-491b-8757-fd13b6ad4b39)  
<br/>
2. tar.gz 파일 우클릭하여 링크 주소 복사  

![image](https://github.com/jisoo449/TIL/assets/48276691/7def2218-f196-4c97-b266-dfc6a86fb742)  

<br/>
3. <code>wget https://github.com/vicgeralds/vitetris/archive/refs/tags/v0.59.1.tar.gz</code> 명령어를 사용하여 tetris 파일 설치
<br/>
4. 해당 파일을 /game 디렉토리 아래에 옮긴 후 압축을 푼다.  

```
$ mkdir game                    #game 디렉토리 생성
$ mv v0.59.1.tar.gz ./game/     #압축파일 이동
$ cd game                        
$ tar -xvzf v0.59.1.tar.gz      #압축 풀기
```

<br/>

5. 이 테트리스 프로그램을 실행하려면 개발에 필수적인 것들이 설치되어야 한다. 아래 명령어를 따라 치면서 C를 빌드할 때 필수적인 라이브러리들을 설치 해 보자.  

```
$ sudo apt-get install build-essential
$ ./configure                             #필요한 셋업을 실행하고 make를 입력해 컴파일을 실행한다.
```

<br/>
6. vitetris-0.59.1 디렉토리로 이동하여 <code>./tetris</code> 를 입력하면 파일이 실행된다.
<br/><br/><br/>


### 게임 실행을 통한 프로세스 감시
터미널을 두 개 더 열고, 한 개는 listen, 한 개는 connect로 연결 해 보자

```
terminal 1
$ ./tetris listen 8888
```

```
terminal2
$ ./tetris connect 8888 {listen중인 IP의 주소}
```

기존의 터미널에서 <code>netstat -anp | grep 8888</code> 로 확인하면 테트리스 게임의 접속자들을 확인할 수 있다.  
![image](https://github.com/jisoo449/TIL/assets/48276691/9e01dbf6-af30-47c0-8ddb-76137ef50a67)  
위 결과를 볼 때 현재 테트리스 게임을 하고 있는 포트는 8888, 59288포트임을 확인할 수 있다.   
<br/>

`ps -ef|grep tetris`를 입력해서 실행중인 프로세스 확인 해 보자.  
![image](https://github.com/jisoo449/TIL/assets/48276691/36ccb0ff-e125-461e-b1e3-f46430b54eb2)  
현재 테트리스를 실행중인 프로세스의 id는 1919, 1970임을 확인할 수 있다. 만약 이들의 통신을 강제로 종료하려면 `sudo kill -9 1919 1970`를 입력하면 된다.
해당 명령어를 입력하면 두 프로세스가 실행중이던 게임이 종료된다.  
<br/>
위 사진에서 테트리스를 실행중인 두 프로세스의 tty가 pts/6, pts5임을 확인하였다.
만약 두 프로세스를 아예 접속하지 못하게 하고 싶다면 `ps -ef|grep “pts”`를 입력해 테트리스를 실행한 pts/5, pts6의 의 프로세스 Id를 확인한 뒤 
`sudo kill -9 PID`를 입력하여 이를 죽인다.  
![image](https://github.com/jisoo449/TIL/assets/48276691/42b05582-bad5-43ca-ab38-1e5d90911834)  


### | 추가
리눅스 터미널에서 `w`를 입력하면 접속중인 사용자를 볼 수 있다. 
만약 관제팀으로 들어가게 된다면 해당 명령어를 입력해 이상한 접속을 하는 사용자를 구분할 수 있을 것이다.    
<br/>
해커들이 제일 처음 하는 일이 w로 볼 수 있는 자신의 정보를 지우는 것 이다.
ps -ef|grep “\-bash”
