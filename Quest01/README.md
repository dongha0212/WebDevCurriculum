# Quest 01. HTML과 웹의 기초

## Introduction
* HTML은 HyperText Markup Language의 약자로, 웹 브라우저에 내용을 표시하기 위한 가장 기본적인 언어입니다. 이번 퀘스트를 통해 HTML에 관한 기초적인 사항들을 알아볼 예정입니다.

## Topics
* HTML의 역사
  * HTML 4.01, XHTML 1.0, XHTML 1.1
  * XHTML 2.0과 HTML5의 대립
  * HTML5와 현재
* 브라우저의 역사
  * Mosaic와 Netscape
  * Internet Explorer의 독점시대
  * Firefox와 Chrome의 등장
  * iOS Safari와 모바일 환경의 브라우저
  * Edge와 Whale 등의 최근의 Chromium 계열 브라우저
* HTML 문서의 구조
  * `<html>`, `<head>`와 `<body>` 등의 HTML 문서의 기본 구조
  * 시맨틱 엘리먼트
  * 블록 엘리먼트와 인라인 엘리먼트의 차이

## Resources
* [MDN - HTML](https://developer.mozilla.org/ko/docs/Web/HTML)
* [HTML For Beginners](https://html.com/)
* [History of the web browser](https://en.wikipedia.org/wiki/History_of_the_web_browser)
* [History of HTML](https://en.wikipedia.org/wiki/HTML)
* [StatCounter](https://gs.statcounter.com/)

## Checklist
* HTML 표준의 역사는 어떻게 될까요?
* A: HTML의 초기 버전들: HTML은 1991년에 Tim Berners-Lee가 개발한 최초의 웹 문서 언어로 시작되었습니다. 초기에는 버전 번호가 없었으며, 각각의 버전은 웹 커뮤니티의 발전에 따라 새로운 기능이나 요구 사항을 반영하여 개발되었습니다.

HTML 2.0: 1995년에 표준화되었으며, 초기 웹 페이지를 만들기 위한 기본적인 구조를 정의했습니다.

HTML 3.2: 1997년에 발표되었으며, 이미지 맵, 테이블 등과 같은 새로운 기능을 도입했습니다.

HTML 4.01: 1999년에 발표되었으며, 다양한 웹 브라우저에서 일관된 동작을 보장하기 위해 노력했습니다.

XHTML 1.0: 2000년에 발표되었으며, XML 기반의 HTML 버전으로, 엄격한 문법을 갖추고 XML의 장점을 가지고 있었습니다.

HTML5: 2014년 표준으로 발표되었으며, 오디오, 비디오, 그래픽, 드래그 앤 드롭 등과 같은 다양한 멀티미디어 기능을 지원하는 새로운 표준입니다.
___
  * HTML 표준을 지키는 것은 왜 중요할까요?
  * XHTML 2.0은 왜 세상에 나오지 못하게 되었을까요?
  * HTML5 표준은 어떤 과정을 통해 정해질까요?
* 브라우저의 역사는 어떻게 될까요?
  * Internet Explorer가 브라우저 시장을 독점하면서 어떤 문제가 일어났고, 이 문제는 어떻게 해결되었을까요?
  * 현재 시점에 브라우저별 점유율은 어떻게 될까요? 이 브라우저별 점유율을 알아보는 것은 왜 중요할까요?
  * 브라우저 엔진(렌더링 엔진)이란 무엇일까요? 어떤 브라우저들이 어떤 엔진을 쓸까요?
  * 모바일 시대 이후, 최근에 출시된 브라우저들은 어떤 특징을 가지고 있을까요?
* HTML 문서는 어떤 구조로 이루어져 있나요?
  * `<head>`에 자주 들어가는 엘리먼트들은 어떤 것이 있고, 어떤 역할을 할까요?
  * 시맨틱 태그는 무엇일까요?
    * 시맨틱 엘리먼트를 사용하면 어떤 점이 좋을까요?
    * `<section>`과 `<div>`, `<header>`, `<footer>`, `<article>` 엘리먼트의 차이점은 무엇인가요?
  * 블록 레벨 엘리먼트와 인라인 엘리먼트는 어떤 차이가 있을까요?

## Quest
* [이 화면](screen.png)의 정보를 HTML 문서로 표현해 보세요. 다만 CSS를 전혀 사용하지 않고, 문서의 구조가 어떻게 되어 있는지를 파악하여 구현해 보세요.
  * [CSS Naked Day](https://css-naked-day.github.io/)는 매년 4월 9일에 CSS 없는 웹 페이지를 공개하여 내용과 마크업에 집중한 HTML 구조의 중요성을 강조하는 행사입니다.
* 폴더에 있는 `skeleton.html` 파일을 바탕으로 작업해 보시면 됩니다.
  * 화면을 구성하는 큰 요소들을 어떻게 처리하면 좋을까요?
  * HTML 문서상에서 같은 층위에 비슷한 요소들이 반복될 때는 어떤 식으로 처리하는 것이 좋을까요?

## Advanced
* XML은 어떤 표준일까요? 어떤 식으로 발전해 왔을까요?
* YML, Markdown 등 다른 마크업 언어들은 어떤 특징을 가지고 있고, 어떤 용도로 쓰일까요?
