# Quest 01. Hello, HTML


## Introduction
* HTML은 HyperText Markup Language의 약자로, 웹 브라우저에 내용을 표시하기 위한 가장 기본적인 언어입니다. 이번 퀘스트를 통해 HTML에 관한 기초적인 사항들을 알아볼 예정입니다.

## Topics
* 브라우저의 역사
  * Mosaic
  * Netscape
  * Internet Explorer
  * Firefox
  * Chrome
  * Safari (for iOS)
* HTML 표준의 역사
  * HTML 4.01
  * XHTML 1.0, XHTML 1.1
  * XHTML 2.0
  * HTML5
* HTML 문서의 구조
* HTML 문서의 엘리먼트
  * Semantic elements
  * Block-level elements vs Inline elements

## Resources
* 검색

## Checklist
* HTML 4.x 이후의 HTML 표준의 변천사는 어떻게 되나요?
* MS와 IE는 왜 역사의 죄인이 되었을까요?
* `<section>`과 `<div>`, `<header>`, `<footer>`, `<article>` 엘리먼트의 차이점은 무엇인가요?

1. <section> html5에서 문서의 섹션을 정의한다. 일반적으로 제목이 있는 주제를 갖는 내용들의 그룹
<section>
<h1>WWF</h1>
<p>The world wide fund for Nature(WWF)is..</p>
</section>


2. <div> 브라우저와 개발자에게 아무 의미도 알려주지 않는 비 시멘틱 요소

3. <header> 문서 헤더 또는 섹션 헤더 지정하는 것 : 소개 내용에 대한 컨테이너로 사용되어야한다. 문서에 여러 header 요소를 포함할 수 있다
<article>
<header>
<h1>Internet Explorer</h1>
<p><time pubdate datetime="2017-06-02"></time></p>
</header>
<p>Windows Internet Explorer 9 was realeased to the public on March 14</p>
</article>

4. <footer> 문서나 섹션의 바닥글 지정 : 바닥글은 일반적으로 문서의 작성자, 저작권 정보, 이용약관에 대한 링크, 연락처 정보를 포함한다. 문서에 여러 footer 요소를 포함할 수 있다.
<article>
<footer>
<p>Posted by:Hege Refsnes</p>
</footer>
</article>

5. <article> 독립적인 자체적으로 만족되는 내용을 지정함 : 웹사이트의 나머지 부분과는 독립적으로 배포될 수 있어야한다 ex) 뉴스기사, 논평, 포럼 게시물, 블로그 포스트
<article>
<h1> Internet Explorer </h1>
<p>Windows Internet Explorer9 was relased to the public on March, 14, 2011 </p>
</article>


* 블럭 레벨 엘리먼트와 인라인 엘리먼트의 차이는 무엇일까요?
블럭 레벨 : HTML문서 상에서 전반적인 흐름을 유도하는 컨텐츠
인라인 : 그 큰 컨텐츠 흐름 안에서 별도의 표현을 하는 컨텐츠 카테고리로서 인식됨 
1. 블럭 레벨 엘리먼트는 <body>요소 안에서만 표현되도록 함. 이러한 블록 레벨 요소들은 해당 요소 이전 요소와 이후 요소를 줄바꿈하는 특징 가짐.
- 서식 : 블록레벨 요소는 새로운 라인에서 시작함
- 컨텐츠 모델 : 블록레벨 요소는 인라인 요소나 다른 블록레벨 요소를 포함할 수 있다. 그래서 블록요소가 인라인 요소보다 더 큰 구조를 만들어 낼 수 있다는 관점을 가짐

## Quest
* [이 그림](github.png)은 github의 웹사이트 레이아웃입니다. 이 레이아웃의 정보를 HTML 문서로 표현해 보세요.
* CSS를 전혀 사용하지 않고, 문서의 구조가 어떻게 되어 있는지를 파악하여 구현해 보세요.
  * [CSS Naked Day](http://meiert.com/en/blog/20150319/css-naked-day/)는 매년 4월 9일에 CSS 없는 웹 페이지를 공개하여 내용과 마크업에 집중한 HTML 구조의 중요성을 강조하는 행사입니다.
* 폴더에 있는 `skeleton.html` 파일을 바탕으로 작업해 보시면 됩니다.
