# CSS
CSS는 HTML이 실제 표시되는 방법을 지정하여 콘텐츠 구조를 꾸며주는 정적 언어로 웹의 시각적인 표현을 담당한다
# CSS 문법
h1, color, red 세 개의 단어가 있는데 각각 선택자, 속성, 값이라고 한다
- 선택자(selector) : 무엇을 꾸밀지 정한다
- 속성(property) : 어떤 모양을 꾸밀지 정한다
- 값(value) : 어떻게 꾸밀지 정한다
```
selector { property: value }
```
property와 value를 합쳐서 선언이라고 한다                      
세미클론으로 구분하여 선택자안에 여러 선언을 넣을 수 있다                
값에 공백이 있으면 따옴표로 감싼다            
# CSS 선언 방식
1. 인라인 방식                
HTML 요소의 style 속성에 직접 작성하는 방식
2. 내장 방식              
HTML <style></style>안에 작성하는 방식
3. 링크 방식                
HTML 를 이용하여 외부 문서로 CSS를 불러와 적용하는 방식
4. @import 방식                 
CSS @import를 이용하여 외부 문서로 CSS를 불러와 적용하는 방식
# CSS 선택자
### * 선택자
모든 태그를 선택하는 선택자
```
* {
    //css code
}
```
### Tag 선택자
주어진 이름의 태그를 선택하는 선택자
```
body {
    /*body css code*/
}

header {
    /*header css code*/
}
```
### class 선택자
주어진 이름의 클래스를 선택하는 선택자 .을 붙여 클래스임을 구분한다
```
.name {
    /*name class css*/
}
```
### id 선택자
주어진 이름의 아이디를 선택하는 선택자 #을 붙여 아이디임을 구분한다
```
#title {
    /*title id css*/
}
```
### 그룹 선택자
그룹 선택자는 여러 선택자를 같이 사용하고자 할 떄 사용한다
```
h1, h2 {
 /* 그룹 css*/
}
```
