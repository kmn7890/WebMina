# Quest 02. Hello, CSS


## Introduction
* CSS는 Cascading StyleSheet의 약자입니다. 웹브라우저에 표시되는 HTML 문서의 스타일을 지정하는 (거의) 유일하지만 다루기 쉽지 않은 언어입니다. 이번 퀘스트를 통해 CSS의 기초적인 레이아웃 작성법을 알아볼 예정입니다.

## Topics
* CSS 기초 문법
선택자 : 스타일링하고 싶은 HTML요소나 부여한 ID나 class
선언부 : 속성:속성값 (property:value)
h1 {color:blue; font-size:12px;}
각각의 선언은 속성과 속성값을 :(콜론)으로 구분한다

* CSS를 HTML에 적용하는 세 가지 방법
  * Inline Style
  * `<style>`
  * `<link rel="stylesheet" href="...">`
* 레이아웃을 위해 몇 가지 중요한 속성들
  * `position`
  * `left`/`top`
  * `display`
  * `width`/`height`
  * `display: flex;`
  * CSS Box Model
* 브라우저별 Developer tools

## Resources
* [MDN - CSS](https://developer.mozilla.org/ko/docs/Web/CSS)
* [모던 웹 디자인을 위한 HTML5+CSS3 입문](http://www.yes24.com/24/Goods/15683538?Acode=101), 한빛미디어
* [웹 디자인 2.0 고급 CSS](http://www.yes24.com/24/Goods/2808075?Acode=101), 에이콘출판사
* [Centering in CSS: A Complete Guide](https://css-tricks.com/centering-css-complete-guide/)
* [A complete guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
* http://webdir.tistory.com/338
* http://naradesign.net/wp/2008/05/27/144/comment-page-1/
## Checklist
* CSS를 HTML에 적용하는 세 가지 방법의 장단점은 무엇인가요?
1) Inline Style
HTML의 style속성을 이용하여 HTML태그 내에 스타일 지정
<p style="color:gray;">이 문단의 색상은 회색으로 지정됨 </p>
장점: 직관적으로 사용이 가능함
단점: 내용과 스타일의 분리 그리고 이로 인한 스타일 일괄변경의 효율성은 떨어짐

2) `<style>`
내부 스타일 시트
<head>와 </head>사이에 스타일을 정의하는 방법
장점: 한 문서에만 해당하는 스타일을 지정할 때 사용
단점: HTML문서마다 스타일을 매번 지정해줘야함

3) `<link rel="stylesheet" href="...">`
외부 스타일 시트
css라는 확장자를 가진 스타일 시트 파일을만들고 이 파일을 HTML문서에 연결하여 사용하는 방법
장점: 홈페이지 전체의 스타일을 일관성있에 유지하면서 변경시에도 일괄적으로 변경되므로 홈페이지 제작의 효율성을 극대화할 수 있음
단점: 외부 스타일 시트 파일을 지속적으로 관리해주면서 HTML문서를 만들어 나가야하기에 불편한 경우가 있음. 그리고 외부 스타일 시트 파일이 지나치게 복잡해지면 관리가 어려워서 노하우 필요

* 여러 개의 CSS 규칙이 한 개의 대상에 적용될 때, 어떤 규칙이 우선순위를 가지게 되나요?
- 선택자 우선순위 :
!important  > 인라인 스타일 > 아이디 선택자 > 클래스/속성/가상 선택자 > 태그 선택자 > 전체 선택자

- 삽입위치 우선순위
(0)최종 사용자가 연결한 CSS파일 안의 !important규칙 (1)<head>안의 <style> 내부스타일시트 (2) <style>안의 @import문 (3)<link rel="stylesheet" href="...">로 연결된 CSS파일 (4) <link rel="stylesheet"로 href="..."> 연결된 CSS파일 안의 @import문 (5)최종 사용자가 연결한 CSS파일 (6) 브라우저 안의 기본 스타일시트

* 어떤 박스가 `position: absolute;`인 속성을 갖는다면, 그 위치의 기준점은 어디가 되나요? 자신의 부모, 조상 객체 중에 relative 속성이 있는 것을 찾아 그 객체를 좌표 기준으로 삼음
div {position:relative}
position속성의 속성값 static, relative, absolute, fixed
중
1) {position: static} : CSS에서 position 속성을 선언하지 않았을 때의 기본값

2) {position: relative} : 상대위치, 본래 자신의 위치를 기준(자신의 분신을 놓아두고 이동한다고 생각할 수 있음)으로 좌표 속성을 통해 이동할 수 있음. 기본적으로 float 속성으로 객체를 정렬했으면 position:relative로 세밀한 조정 가능. 다른 객체에 영향을 주지 않음.
top, right, bottom, left 4가지로 좌표속성 지정 가능
div{
  position:relative;
  top: 100px;
  left: -100px;
}

3) {position: absolute} : 절대위치, 본래 자신의 위치 혹은 relative속성이 선언된 객체를 기준으로 좌표속성을 통해 이동할 수 있음. 공중에 붕 뜬 상태로 이해할 수 있음. 그 어떤 다른 객체에도 영향을 끼치지 않고 단독적으로 위치를 잡을 수 있음. absolute값을 갖는 객체는 float 속성을 선언해도 소용없이, 자신의 부모, 조상 객체 중에 relative 속성이 있는 것을 찾아 그 객체를 좌표 기준으로 삼음

4) {position: fixed} : 고정위치, 웹브라우저의 윈도우를 기준으로 좌표속성을 통해 이동. 스크롤이 생겨도 화면에서 사라지지 않는 붙박이 성질을 갖고 있음, 메뉴나 검색 필드가 포함된 상단 헤더를 fixed로 해놓으면 좋음

* 가로나 세로로 여러 개의 박스가 공간을 채우되, 그 중 한 개의 박스만 가변적인 크기를 가지고 나머지 박스는 고정된 크기를 갖게 하려면 어떻게 해야 할까요?
한개의 박스에 overflow:hidden을 설정하고 나머지 박스는 float:right이나 float:left를 주고 그 크기를 설정함

* `float` 속성은 왜 좋지 않을까요?
float 속성이 부여된 엘리먼트는 좌측이나 우측으로 배치되면서 주변 컨텐츠의 배치에도 영향을 줌.
그러나 부모 element의 높이에는 영향을 주지 못함.
다단 컬럼형 레이아웃을 시도할 때 주변 엘리먼트들이 원하는 상태로 배치되게 해주기 위해서 ₩clear₩속성을 사용하면  
(1) float를 부모 element에 줌
container{float:left}이런식 => 조상 엘리먼트들이 겹겹이 존재하면 모두 float시켜야하는 단점
(2) overflow를 부모 element에 줌
container{overflow:hidden} => 자식의 너비가 넘치는 경우 넘치는 부분이 잘리므로 안전한 방법은 아님
(3) 부모 element에 빈 element로 clear하는 방법
container영역이 끝나기 직전 빈 element를 넣고 빈 element에 clear:both 속성을 부여. 하지만 의미 없는 빈 element를 사용하므로 권장되는 방법은 아님. 실무에서는 clear{clear:both; height:0; overflow:hidden;}처리하여 스스로 높이를 갖지 않고 보이지 않게 처리함
(4) float를 가상선택자 after로 clear하는 방법  가상선택자 (가상클래스 & 가상엘리먼트)
:link, :visited, :hover, :active, :focus는 가상 클래스 => 특정 element에 대해 아무런 class부여하지 않아도 마치 역동적으로 class를 변경한 것과 같은 효과를 낼 수 있는 것들 이미 있는 element에 조합해서 사용
A:link{color:red} 방문하지 않았던 연결
A:visited{color:blue} 방문했던 연결
A:hover{color:yellow} 사용자가 마우스를 연결에 올려놓았을 때
A:active{color:lime} 활성 연결
A:focus{color:purple} 사용자가 키보드 이벤트 또는 텍스트 입력 양식에 입력할 때

:first-line, :first-letter, :before, :after는 가상 엘리먼트 => HTML문서상 존재하지 않는 컨텐츠를 출력시킴

=> container:after{content:""; display:block, clear:both;}

* Flexbox(Flexible box)를 사용할 때의 한계점은 무엇인가요?
- CSS3의 새로운 레이아웃 모드
- flexbox를 사용하면 페이지 레이아웃이 다른 화면 크기와 다른 디스플레이 장치를 수용해야할 때 예상대로 작동함
http://www.beautifulcss.com/archives/2812
한계점 : IE10이하에서는 작동하지 않음

## Quest
* 아래의 그림들은 모두 전체적으로 창의 크기에 꽉 차야 하며, 창의 크기가 일정 크기 이상일 경우 전체 창 크기가 어떻게 바뀌되더라도 그림에 맞게 각 박스의 크기가 조절되어야 합니다.
* **주의사항**
  * HTML 파일은 수정하면 안됩니다.
  * `float` 속성과 `calc()`함수를 사용하지 않고 해 보세요!
* [이 그림](layout1.png)을 flexbox를 쓰지 않고 구현해 보세요. `skeletons/layout1.html` 파일에 링크된 `skeletons/layout1.css` 파일을 수정하면 됩니다.
* [이 그림](layout2.png)을 flexbox를 쓰지 않고 구현해 보세요. `skeletons/layout2.html` 파일에 링크된 `skeletons/layout2.css` 파일을 수정하면 됩니다.
* [이 그림](layout3.png)을 flexbox를 쓰지 않고 구현해 보세요. `skeletons/layout3.html` 파일에 링크된 `skeletons/layout3.css` 파일을 수정하면 됩니다.
* 위와 같은 그림을 flexbox를 써서 구현해 보세요. `skeletons/layout4.html` 파일에 링크된 `skeletons/layout4.css` 파일을 수정하면 됩니다.
