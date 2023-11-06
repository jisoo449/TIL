## 개요
본 글은 파이썬을 사용할 때 지켜야 할 규칙을 간략히 정리한 글이다. 해당 내용은 원칙적으로 권장되는 규칙이나, 회사나 팀 등에서 내부적으로 사용하는 규칙이 있다면 그것을 따르는 것이 좋다.  
<br/>
<b>목차</b>
  - [인덴션](#인덴션)
  - [네이밍 스타일의 종류](#네이밍-스타일의-종류)
  - [파이썬의 네이밍 컨벤션](#파이썬의-네이밍-컨벤션)  
<br/><br/><br/>


### 인덴션
한 인덴션 레벨은 4개의 공백을 가진다.
```
# Add 4 spaces (an extra level of indentation) to distinguish arguments from the rest.
def long_function_name(
        var_one, var_two, var_three,
        var_four):
    print(var_one)
```
하지만 꼭 공백이 꼭 네개일 필요는 없다. 코드를 돌려 보면 공백이 한 개 일 때도, 7개일 때도 코드는 잘 동작한다. 여기서 중요한 것은 동일한 인덴션 레벨은 동일한 공백 개수를 가져야 한다는 것이다.  
<br/><br/>


### 네이밍 스타일의 종류
| 종류 | 기법 |
|--------------|----------------------|
|카멜 케이스(Camel Case)|단어가 합쳐진 부분마다 시작 문자를 모두 대문자로 한다. 이는 이름의 맨 앞글자는 소문자로 표기하는 lower camel case와 모든 시작글자는 대문자로 하는 upper camel case로 나뉜다. <br/>ex)<code>lowerCamelCase</code>, <code>UpperCamelCase</code>|
|스네이크 케이스(Snake Case)|영어와 언더바로 구성된다. 두 개 이상의 단어가 있다면 언더바(_)로 연결한다.<br/>ex)<code>snake_case</code>, <code>SNAKE_CASE</code>|
|케밥 케이스(Kebab Case)|스네이크 케이스와 유사하다. 언더바 대신 하이픈(-)으로 단어를 연결한다.<br/>ex)<code>kebab-case</code>|
|고유 접두사 사용|이름을 그룹화 하는 데 사용된다. 파이썬에서는 많이 사용되지는 않는다.<br/>eex)<code>st_mode</code>, <code>st_size</code>|
|<code>_single_leading_underscore</code>|내부적으로 사용되는 변수이다.|
|<code>single_trailing_underscore_</code>|파이썬 키워드와의 충돌을 피할 때 사용한다.|
|<code>__double_leading_underscore</code>|클래스 속성으로 사용되면 그 이름을 변경한다.<br/>ex. FooBar에 정의된 __boo는 _FooBar__boo로 변경됨|
|<code>__double_leading_and_trailing_underscore__</code>|사용자가 조정할 수 있는 네임스페이스 안의 특별한 속성이나 객체의 이름으로 사용한다.|

이외에도 다양한 종류의 표기법이 존재한다. 개중에서 가장 많이 쓰이는 컨벤션은 카멜, 스네이크 이 두 개 이다.  
<br/><br/>


### 파이썬의 네이밍 컨벤션
<b>| 금지되는 이름</b>  
- 숫자로 시작하는 이름
- 'l'(소문자 엘), 'O'(대문자 오), 'I'(대문자 아이) 단일 문자로 이루어진 이름
- ASCII와 호환되지 않는 이름
<br/>

<b>| 클래스 이름</b><br/>
클래스명은 일반적으로 Upper Camel Case(Pascal Case)를 사용한다.  
ex) <code>class UpperClass: </code>
<br/>

<b>| 함수 및 변수명</b><br/>
파이썬에서 함수와 변수의 이름은 소문자로 작성하고, 필요에 따라 밑줄로 단어를 구분한다.  
ex) <code>varname</code>, <code>variable_name</code>
<br/>

<b>| 전역변수명</b><br/>
전역변수의 네이밍 컨벤션은 위에 적힌 함수 및 변수명의 규칙과 거의 동일하다. 특정 모듈에 선언된 전역변수는 하나의 모듈 안에서만 사용하는 것을 권장한다.  
<code>from M import *</code>를 통해 가져온 모듈은 [<code>__double_leading_and_trailing_underscore__</code>](#네이밍-스타일의-종류)을 사용하거나 <code>__all__</code> 메커니즘을 사용한다.  
+) <code>__all__</code> 메커니즘이란?  
  파이썬에서 모듈에서 외부로 공개되어야 하는 식별자(identifier)들을 정의하는 데 사용되는 특별한 변수로, 어떤 식별자들이 공개되어야 하는지를 명시적으로 지정할 때 사용합니다.
<br/>

<b>| 메소드와 매개변수</b><br/>
인스턴스 메소드는 항상 첫 번째 인자로 <code>self</code>를 사용하고, 클래스 메소드는 <code>cls</code>를 첫번째 인자로 사용한다. 만약 매개변수 이름이 예약 키워드와 충돌하는 경우 뒤에 언더바를 추가하는 것이 좋다.  
ex)<code>class_</code>   
<br/>

<b>| 메소드명과 객체명</b><br/>
위에 서술한 함수 및 변수명의 네이밍 컨벤션을 따른다.  
public이 아닌 메서드 및 인스턴스 변수의 이름 앞에는 언더바 하나('_')를 붙인다.  
서브클래스와 이름 충돌을 방지하려면 언더바 두 개('__')를 사용하여 파이썬의 맹글링 규칙을 호출한다.  
<br/>

<b>| 상수</b><br/>
상수는 일반적으로 모듈레벨에서 정의되며 대문자와 언더바('_')로 정의된다.<br/>
ex)<code>MAX_OVERFLOW</code>
<br/>




<br/><br/>
이 밖에도 파이썬을 사용할 때 권장되는 다양한 규칙들이 있다. 아래의 사이트에 잘 정리되어 있으니 필요할 때 참고하면 된다.  
출처: https://peps.python.org/pep-0008/
