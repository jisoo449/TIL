## 리눅스 설정
### 1. 부팅모드 변경
처음 리눅스에 접속하면 GUI로 창이 열리는 것을 확인할 수 있다. CLI 사용에 익숙해지기 위해 부팅모드를 변경해 보자.  
1. 화면 좌측 하단에 메뉴 버튼을 클릭하여 Teminal을 열자.  
![image](https://github.com/jisoo449/TIL/assets/48276691/d167472a-9b40-4a53-8397-d07a315df708)  
<br/>

3. 터미널에 접속하여 <code>sudo systemctl set-default multi-user.target</code>를 입력한다.<br/>
![image](https://github.com/jisoo449/TIL/assets/48276691/72957142-7974-4af3-b826-01ea83ccd399)  

<br/>
이후 가상 컴퓨터를 재시작하면 cli 모드로 컴퓨터가 열린다.   
<br/><br/>  

### 2. 메모리 크기 줄이기
가상머신을 생성할 때에는 속도 때문에 메모리 크기를 따로 건드리지 않았다.  
하지만 이후 진행할 수업에서는 메모리가 큰 프로그램을 돌리지 않을 것이므로 메모리 사이즈를 줄여보자
메모리 사이즈를 줄이는 동작은 인스턴스가 종료된 상태에서만 가능하다.  

1. 인스턴스 우클릭 -> 설정 -> 메모리로 들어간다.  
![image](https://github.com/jisoo449/TIL/assets/48276691/c3a1876e-ceb2-4201-8c56-d09cbce0d7fd)
<br/>

2. 메모리 크기를 1GB로 변경한다.<br/>
![image](https://github.com/jisoo449/TIL/assets/48276691/86b69f70-fb92-4c03-8424-a99b97f3cdb3)
<br/>

3. 인스턴스를 실행한 후 <code>sudo apt-get update</code> 명령어를 사용하여 변경사항을 적용한다.<br/>
![image](https://github.com/jisoo449/TIL/assets/48276691/62f780b0-0dd7-440a-8c8f-d7f04337b808)
<br/><br/>

### 3. 스냅샷
스냅샷이란 특정 시점에 스토리지의 파일 시스템을 포착해 별도의 파일이나 이미지로 저장 및 보관하는 기술을 말한다. 스냅샷을 찍으면 데이터 복원이 가능해지는 장점이 있다.  
스냅샷을 띄울 땐 필수 정보들(id, pwd, 현재 진행상황 등)을 함께 커밋한다.   

1. 인스턴스 우클릭 -> 스냅샷 -> Take Snapshot <br/>
![image](https://github.com/jisoo449/TIL/assets/48276691/60fea0c9-0da4-4896-b409-43532de4a92e)
<br/>

2. 스냅샷 설명 적기<br/>
![image](https://github.com/jisoo449/TIL/assets/48276691/f676faf2-56c9-45c6-bb9a-56cdeb18855f)
<br/>

이후 스냅샷 매니저에 들어가면 지금까지 찍은 스냅샷을 조회할 수 있다. 
