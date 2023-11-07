### 목차
1. [리눅스란?](#1.-리눅스란)
2. [우분투 설치](#2-우분투-설치)
3. [VMware 설치](#3-VM-ware-설치)
4. [가상 서버 생성](#4-가상-서버-생성)
5. [원격 서버 접속](#5-원격-서버-접속)
<br/><br/>

## 1. 리눅스란
### 1.1. 등장 배경
1950년대에 들어서면서 컴퓨터가 개발되기 시작했다. 컴퓨터를 사용하기 위해서는 필연적으로 소프트웨어가 필요했고, 따라서 이 때 당시에는 모든 소프트웨어가 공개적으로 개발되었으며, 소스코드 또한 모두 공개되었다.  
1960년대에 들어서면서 유닉스 운영체제가 만들어지면서 밀접하게 연결되어 있던 소프트웨어와 하드웨어를 구분할 수 있게 되었다. 처음 유닉스가 만들어졌을 당시에는 유닉스의 모든 소스코드가 공개되었다.
하지만 얼마 지나지 않아 프로그램의 상품화의 중요성이 대두되기 시작하였고 80년대 들어서면서 유닉스를 포함한 많은 프로그램이 제품화되어 유통되기 시작한다. 
이에 1984년도에 GNU 프로젝트가 시작되게 된다. GNU 프로젝트의 목적은 '모두가 공유할 수 있는 소프트웨어를 만드는 것' 으로, GNU프로젝트에서 제작한 소프트웨어를 지원함으로써 
컴퓨터 프로그램의복제, 변경, 소스코드의 사용에 대한 제한을 철폐하고자 하였다. 이러한 배경 아래에서 리눅스가 등장하게 되었다.  
<br/>
### 1.2. 리눅스의 개요
리눅스는 무료 버전의 유닉스라고 보면 된다. 리누스 토르발스가 1991년에 0.01 버전을 최초로 작성하고, 이후 92년도에 0.02 버전을 공개하면서 시작되었다.  
리눅스는 커널만 제공하기 때문에 이를 쉽게 사용하기 위해서는 쉘 스크립트를 사용하게 된다.  
리눅스에는 다양한 배포한이 존재한다. 유명한 배포판으로는 데비안(Debin)과 우분투(Ubuntu)가 있다. 우분투 배포판은 우분투 데스크톱과 우분투 서버 두 가지가 존재한다. 
<br/><br/><br/>

## 2. 우분투 설치
윈도우에서 우분투를 설치하는 방법은 크게 두 가지로 나뉜다. 첫 번째 방법은 [우분투 홈페이지](#https://ubuntu.com/download)에 들어가 우분투를 설치하는 방법이고, 
두 번째 방법은 MS store에서 우분투를 설치하는 방법이다.  
하지만 MS store에서 설치하는 우분투는 단순히 윈도우에서 우분투를 더 쉽게 사용할 수 있도록 하는 하위 시스템일 뿐이지, 윈도우 운영체제를 우분투로 바꾸어 주는 것은 아니다.  
따라서 가상 컴퓨터에 우분투를 운영체제로 설치하기 위해서는 우분투 홈페이지에 올라와 있는 iso를 설치해야 한다.  
<br/>
방법 1. [우분투 홈페이지에](https://ubuntu.com/download)에 접속하여 Download Ubuntu Desktop이라고 적힌 녹색 버튼을 누른 후, 다음 페이지에서 Download [우분투 버전] 이라고 적힌 녹색 버튼을 누르면 자동으로 우분투 iso파일 설치가 시작된다.
![image](https://github.com/jisoo449/TIL/assets/48276691/73271a76-1f80-4dfb-b789-c570f3ad70da)
![image](https://github.com/jisoo449/TIL/assets/48276691/4535a23f-d8f6-4d67-b6f3-1762149188d3)
<br/><br/>
방법 2. [우분투 릴리즈 버전](https://releases.ubuntu.com/23.10/)들을 모아둔 페이지에서 원하는 버전을 선택 후 desktop버전 iso파일을 설치한다.
 ![image](https://github.com/jisoo449/TIL/assets/48276691/bf79ec43-7880-4bc1-920e-07c8993ce7ee)
![image](https://github.com/jisoo449/TIL/assets/48276691/36ceb909-bd1b-4938-aa5f-6786d6ae140e)
<br/><br/><br/>

## 3. VM ware 설치
리눅스 설치 및 실행은 VMware workstation Pro 17을 통해 실행할 것이다. 해당 프로그램은 유료이므로 30일 무료 평가판을 사용하자. 
[VMware 홈페이지](https://www.vmware.com/content/vmware/vmware-published-sites/us/products/workstation-pro/workstation-pro-evaluation.html.html.html) 접속 및 Workstation 17 Pro 설치
![image](https://github.com/jisoo449/TIL/assets/48276691/f84697ee-3700-4418-9a53-c0f912738c4a)
<br/><br/>

## 4. 가상 서버 생성
성공적으로 VMware Workstation 17 Pro를 설치했다면 이제는 가상 서버를 생성할 차례이다. 
1. VMware Workstation을 열면 좌측 바를 확인할 수 있다. 여기서 마우스 우클릭하여 New Virtual Machine... 을 클릭한다. 
![image](https://github.com/jisoo449/TIL/assets/48276691/11d0d738-5e4a-46da-8582-8fdf69a5bcdd)

2. Typical을 선택한다.  
![image](https://github.com/jisoo449/TIL/assets/48276691/44ebe742-a4fc-49d1-9e26-9b09238d358a)

3. 이전에 설치한 리눅스 iso파일로 설치한다.  
![image](https://github.com/jisoo449/TIL/assets/48276691/81ccf910-23fe-49d7-94e6-40f2f5249688)
<br/>
이후 쭉 기본설정을 따라가며 설치를 진행하면 된다.

<br/><br/><br/>
## 5. 원격 서버 접속
원격으로 서버를 접속하는 방법은 여러가지가 있다. 대표적인 방법은 푸티를 사용하는 것이나, 본문에서는 VS코드를 사용하여 원격 서버로 접속하는 방법을 알려줄 것이다. 
1. VS코드의 좌측 바에는 Extension 아이콘이 있다. 해당 아이콘을 클릭하여 익스텐션 라이브러리로 들어간다.  
![image](https://github.com/jisoo449/TIL/assets/48276691/a7ca479e-ffdc-4aed-9146-11497bce6fb2)  
2. ssh를 입력하여 맨 위에 나오는 Remote-ssh를 설치한다.  
![image](https://github.com/jisoo449/TIL/assets/48276691/89a76faf-a494-4ab2-b199-07031a1ee855)  
3. 설치 이후 VScode의 좌측 하단에 생긴 파란 버튼을 클릭한다. 상단에 창이 생긴다. 이 창에서 Connect to Host... Remote-ssh 를 클릭한다.  
![image](https://github.com/jisoo449/TIL/assets/48276691/4921d43f-1c6b-4fcd-834d-6ea0478067f0)
4. Add New SSH Host를 선택한다.
![image](https://github.com/jisoo449/TIL/assets/48276691/1ef7d0d4-2113-418a-8c17-c7bb5d6b08ff)
5. 계정명@IP 를 입력한다.  
![image](https://github.com/jisoo449/TIL/assets/48276691/e9d0d368-4554-4e9e-9917-f6a8c89a9735)
6. 맨 상단의 버튼을 클릭한다.
![image](https://github.com/jisoo449/TIL/assets/48276691/8e3cc008-9454-403f-8b81-f45cddec5302)
7. config파일을 열어 port번호와 Host명을 수정해준다.  
![image](https://github.com/jisoo449/TIL/assets/48276691/175e9dd9-8863-4841-a747-4321024ba2f3)
8. 이후 다시 좌측 하단에 있는 파란 버튼을 누른 뒤 Connect to Host -> 추가한 ip주소 를 클릭하면 외부 서버 접속이 완료된다.
<br/>
만약 실행이 되지 않는다면 .ssh 디렉토리 안의 known_hosts파일을 삭제하면 될 것이다. 
