### @Entity
테이블과 값이 매핑(연겶)되는 부분에서 사용하는 어노테이션  
  
getter, setter를 자동으로 생성 해 준다.  
  
  
### @Column
데이터를 연결할 때 프로젝트의 필드명과 데이터베이스의 컬럼명을 매치할 때 사용한다.  
  
작성 예시: ```@Colmn(이름, insertable=?, ...)```  
  
  
### @Data
getter, setter, require contructor  
    
    
### @NoArgsConstructor
기본 생성자를 자동으로 생성  
  
메소드 설정을 통해 접근 제어를 조정할 수 있다(PRIVATE, PROTECTED, PUBLIC)  
  
작성 예시: ```@NoArgisConstructor(AccessLevel.PROTOCOLE)```



참고: https://www.icatpark.com/entry/JPA-%EA%B8%B0%EB%B3%B8-Annotation-%EC%A0%95%EB%A6%AC
