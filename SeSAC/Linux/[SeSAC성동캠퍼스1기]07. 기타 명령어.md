## 기타 명령어
- [링크](#링크)
- [설치](#설치)
- [네트워크 설정](#네트워크-설정)
- [기타 명령어 모음집](#기타-명령어-모음집)
<br/><br/><br/>
### 링크
링크는 크게 두 종류가 있다.
- hard link
    - <code>ln {원본파일} {링크파일}</code>
    - 링크를 연결한 후 파일 정보를 보면 연결된 링크가 1개에서 2개가 된 것을 확인할 수 있다.
      ![image](https://github.com/jisoo449/TIL/assets/48276691/f276e6df-3c7a-4cee-9c71-08070c206f7b)<br/>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↓<br/>
      ![image](https://github.com/jisoo449/TIL/assets/48276691/d0b4dfcc-3a7e-4ad9-af5b-2c9860c93551)
      이 두 파일은 내용도, 이름도 연결되어 있다. bar를 편집하면 foo도 같이 변한다. bar를 삭제하면 foo에 걸린 링크가 1개로 줄어든다. 
- symbolic link
    - <code>ln -s {원본파일} {링크파일}</code>
    - 생성한 바로가기에 원본 파일로 가리키는 화살표가 생성된다.
    - 하드 링크처럼 심볼릭 링크를 편집하면 원본도 함께 수정이 된다.
    - 원본을 삭제한 뒤 링크를 열면 기존에 있던 내용은 사라진 채 빈 파일이 열린다.
<br/><br/>

### 설치
apt나 apt-get 명령어를 사용해 원하는 라이브러리나 프로그램을 설치할 수 있다.  
이 명령어를 사용하면 원하는 프로그램을 http://kr.archive.ubuntu.com/ubuntu focal/main…에서 받아온다.  
이 링크들에 대한 정보는 /etc/apt/sources.list라는 파일에 저장되어 있다. apt-get 명령어가 입력되면 컴퓨터는 해당 파일에 저장된 url들에 apt-get 의 옵션들을 
쿼리로 날려서 찾아 설치를 한다.  
설치한 라이브러리/프로그램의 설명을 보고 싶다면 <code>apt-ache show {설치한라이브러}</code> 명령어를 입력하면 된다.
<br/><br/>

### 네트워크 설정
nmtui 명령어를 사용해 네트워크 정보를 조회 및 설정할 수 있다.  
네트워크 설정 정보는 etc/netplan/ 디렉토리 아래에 존재하며, yaml 확장자를 가진다.  
만약 yaml 파일을 수정하는 방식으로 네트워크를 수정하려 한다면 인덴션을 철저하게 지켜야 한다. 이는 쉽지 않으므로 nmtui 명령어로 관리자 편집기로 들어가 편집하는 방법을 추천한다.  
<br/><br/>

### 기타 명령어 모음집
- 기본 명령어<br/>

|명령어|주요 옵션|설명|
|---------|---------|--------------------------------------|
|ls| -altr| 디렉토리의 리스트를 보여준다. (== dir)|
|vi ||파일 열기|
|man ||명령어의 사용법(==메뉴얼)을 보여준다.|
|cd|| change directory 작업 디렉토리를 변경한다.|
|cp| -rf| 복사 (-rf : 하위디렉토리까지(r) 묻지않고 강제로(f) )|
|mv ||파일 옮기기|
|ln| -s |ln –s 소스 바로가기|
|pwd|| 현재 커서의 위치를 보여준다.|
|alias|| 긴 명령어를 짧게 치환해 준다. ex> alias ls=’ls –altr’|
|touch|| 비어있는 파일(0바이트)을 생성하거나, 존재하는 파일의 시간을 갱신|
|rm| -rf| 파일 삭제 (-rf : 하위디렉토리까지(r) 묻지않고 강제로(f) )|
|mkdir ||디렉토리 생성|
|rmdir|| 디렉토리 삭제|
|cat|| 파일의 내용을 출력시켜준다.|
|head|| 파일 앞부분의 내용을 출력시켜준다. (디폴트 : 10라인)|
|tail|| 파일 뒷부분의 내용 출력 ex> tail –f –n 20 /var/log/message|
|more ||페이지 단위로 출력시켜줄 때. 보조명령어<br/>ex> cat /etc/passwd | more ( == more /etc/passwd)|
|file ||특정 파일의 속성을 출력 ex> file /bin/ls|
|clear ||화면을 지우고 커서를 첫째라인으로.|
|watch ||특정 명령어를 주기적으로 자동 수행 ex> watch ls -al|
|find|| 검색기능 제공 ex> find / -name "passwd" -print|
|grep| -r |파일에서 특정 문자열을 검색한다. (r 옵션은 하위디렉토리까지)<br/>ex> grep “root” -r /var/log/, grep “root” /var/log/secure|
|bzip2 |d |압축. 확장자 .gz2 해제는 bzip2 -d|
|gzip |d| 압축. 확장자 .gz 해제는 gzip –d 또는 gunzip|
|tar|xvf,cvf,z,tvf|tar cvzf : 압축, 묶는다. (ex> tar cvzf 생성파일.tar.gz 대상dir)<br/>tar xvzf : 압축 풀고 tar 풀고(ex> tar xvzf 생성파일.tar.gz)|
|write|id tty|ex> write user25 pts/8 : pts/8터미널을 사용하는 user25에게 메시지를 보낸다.|
|export|| ex> export LANG=ko_KR.UTF-8|
|uname |a |시스템 이름, 커널정보, 빌드날짜 등을 출력|
|arch ||시스템 종류를 출력 (== uname –m)|
|nohup ||로그오프 후에도 실행 프로세스를 유지|
|kill|| 프로세스를 죽인다. ex> kill –9 1111|
|pkill|| 프로세스를 죽인다. ex> pkill –9 httpd|
|umask|| 생성파일의 권한을 설정 ex> umask 0022 (=> 0666 – 0022 = 644)|
|history|| 지난 명령어 목록을 출력한다.|
|exit| |종료|

<br/><br/>
- 네트워크 명령어<br/>

|명령어|주요 옵션|설명|
|---------|---------|--------------------------------------|
|ifconfig ||ifconfig [interface-name] [up/down]  ex> ifconfig eth0 down|
|ping |-b| b: 브로드캐스트 옵션|
|traceroute |-n |경로추적 명령어. (n: 도메인명을 IP로 출력하라==window : d옵션)|
|netstat |anp, i, rn|anp : 프로세스별 네트워크 연결 정보를 출력<br/>i : 네트워크 카드의 사용량 통계<br/>rn : 라우팅 테이블 정보 출력<br/>route n 라우팅 테이블을 설정하거나 조회|
|arp |a, d, n|IP – Mac 주소 매칭정보 출력<br/>a : 전체 출력<br/>n : IP만 출력<br/>d : 삭제|
|dig ||도메인명에 대한 IP를 조회해 온다.|
|ftp|||
|ssh| -p| 원격 접속 명령 (p : 포트번호 지정 옵션)|
|scp |-p |원격 파일 복사 명령 ex> scp  ./file_name  id@ip:/path/|
|ethtool|| 랜카드의 물리적 속성을 출력한다. ex> ethtool  eth0|
|tcpdump ||스니핑 툴(=패킷분석기). ex> tcpdump port 80|
|id ||사용자 아이디 출력|
|w|| 현재 누가 어디에서 무엇을 하는지 정보 출력|
|groups|||
|groupadd|||
|groupdel|||
|sudo ||관리자 명령어 1개를 실행해준다. (/etc/sudoers 파일에서 설정)|
|su|| 관리자로 권한 상승한다. (/etc/sudoers 파일에서 설정)|
|last|| 각 사용자별 마지막 로그인 시간 및 접속 위치(IP) 정보 출력|
|lastlog|| last와 유사하나, 전체 계정(/etc/passwd)에 대한 정보를 출력|
|hostname ||호스트명을 출력하거나 설정(휘발성) ex>hostname  tmp.hack.com|
|host ||특정 호스트의 IP정보를 출력. dig과 유사|
|rdate || rdate –s time.bora.net : 시간 동기화|

<br/><br/>
- 시스템 명령어<br/>

|명령어|주요 옵션|설명|
|---------|---------|--------------------------------------|
|init |0|부팅 명령어 (runlevel : 0 ~ 6)<br/>#   0 - halt ( 서버 종료 )<br/>#   1 - Single user mode<br/>#  2 - Multiuser, without NFS (The same as 3, if you do not have networking)<br/>#   3 - Full multiuser mode<br/>#   4 - unused<br/>#   5 - X11<br/>#   6 - reboot (Do NOT set initdefault to this)|
|reboot ||재부팅|
|shutdown ||== init 0|
|halt ||== init 0|
|yum|install,<br/>update,<br/>upgrade,<br/>remove|ex> yum groupinstall "Development Tools"|
|dmesg|| 시스템 부팅 로그를 출력|
|free|| 메모리 정보를 출력함.|
|df |h |디스크 용량 정보를 출력함.|
|du |h |현재 위치 아래의 디스크 사용량 출력|
|strace ||실행파일의 시스템콜을 출력한다.|
|strings ||파일 안에서 출력 가능한 문자열을 화면에 뿌려준다.|
|lsof|| 파일을 어떤 프로세스가 사용 중인지 출력한다.|
|uptime|| 시스템 부팅시간|
|ps |-ef| 프로세스 정보 출력|
|top ||윈도우의 작업관리자와 같은 역할. 시스템 리소스 정보 출력|
|pstree ||프로세스 트리를 보여준다.|
|mount ||특정 장치를 서버에 로드한다. (ex> mount cdrom /mnt/cdrom)|
|umount|| 특정 장치를 언로드한다. (ex> umount cdrom)|
|sync|| 종료 전 동기화 명령 ( sync;sync;sync;sync;shutdown )|
