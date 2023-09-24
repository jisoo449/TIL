### JPA vs MyBatis
복잡한 요청은 MyBatis, 이외의 것은 JPA를 사용한다. 

### MyBatis to JPA
1.  build.gradle, application.properties 파일 설정을 수정한다.  
    이 때 [인코딩 설정을 utf-8로 수정](#인텔리제이_인코딩_설정_수정_방법)해 주는 것을 잊지 말아야 한다.  



### 인텔리제이 인코딩 설정 수정 방법

  1. 상단 바 File >> Settings... 클릭
  2. 팝업 좌측 바에서 Editor >> File Encodings >> Global, Project Encoding, Properties Files 설정을 UTF-8로 변경
  3. 이후 다시 상단 바에서 Run >> Edit Configurations 클릭
  4. VM options에 """-Dfile.encoding=UTF-8""" 을 추가

참고: https://goddaehee.tistory.com/248
