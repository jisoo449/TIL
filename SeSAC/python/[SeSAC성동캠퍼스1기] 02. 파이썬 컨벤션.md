## 개요
본 글은 파이썬을 사용할 때 지켜야 할 규칙을 간략히 정리한 글이다. 해당 내용은 원칙적으로 권장되는 규칙이나, 회사나 팀 등에서 내부적으로 사용하는 규칙이 있다면 그것을 따르는 것이 좋다.  
<br/>
<b>목차</b>
  - [인덴션](#인덴션)
  - [네이밍 컨벤션의 종류](#네이밍-컨벤션의-종류)
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


### 네이밍 컨벤션의 종류
| 종류 | 기법 |
|--------------|----------------------|
|카멜 케이스(Camel Case)|주로 소문자로 구성된다. 하지만 만약 두 개 이상의 단어의 모음이라면 두 번째 단어부터 첫 스펠링은 대문자로 작성한다.<br/><code>ex)camelCase</code>|
|스네이크 케이스(Snake Case)|소문자와 언더바로 구성된다. 두 개 이상의 단어가 있다면 언더바(_)로 연결한다.<br/><code>ex)snake_case</code>|
|케밥 케이스(Kebab Case)|스네이크 케이스와 유사하다. 언더바 대신 하이픈(-)으로 단어를 연결한다.<br/><code>ex)kebab-case</code>|
|파스칼 케이스(Pascal Case)|단어의 시작 문자는 모두 대문자로 한다.<br/><code>ex)PascalCase</code>|

이외에도 다양한 종류의 표기법이 존재한다. 개중에서 가장 많이 쓰이는 컨벤션은 카멜, 스네이크 이 두 개 이다.  
<br/><br/>


### 파이썬의 네이밍 컨벤션

<br/><br/>
출처: https://peps.python.org/pep-0008/
