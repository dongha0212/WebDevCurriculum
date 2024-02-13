# Quest 02. CSS의 기초와 응용

## Introduction
* CSS는 Cascading StyleSheet의 약자입니다. 웹브라우저에 표시되는 HTML 문서의 스타일을 지정하는 (거의) 유일하지만 다루기 쉽지 않은 언어입니다. 이번 퀘스트를 통해 CSS의 기초적인 레이아웃 작성법을 알아볼 예정입니다.

## Topics
* CSS의 기초 문법과 적용 방법
  * Inline, `<style>`, `<link rel="stylesheet" href="...">`
* CSS 규칙의 우선순위
* 박스 모델과 레이아웃 요소
  * 박스 모델: `width`, `height`, `margin`, `padding`, `border`, `box-sizing`
  * `position`, `left`, `top`, `display`
  * CSS Flexbox와 Grid
* CSS 표준의 역사
* 브라우저별 Developer tools

## Resources
* [MDN - CSS](https://developer.mozilla.org/ko/docs/Web/CSS)
* [Centering in CSS: A Complete Guide](https://css-tricks.com/centering-css-complete-guide/)
* [A complete guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
* [그리드 레이아웃과 다른 레이아웃 방법과의 관계](https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Grid_Layout/%EA%B7%B8%EB%A6%AC%EB%93%9C_%EB%A0%88%EC%9D%B4%EC%95%84%EC%9B%83%EA%B3%BC_%EB%8B%A4%EB%A5%B8_%EB%A0%88%EC%9D%B4%EC%95%84%EC%9B%83_%EB%B0%A9%EB%B2%95%EA%B3%BC%EC%9D%98_%EA%B4%80%EA%B3%84)

## Checklist
`* CSS를 HTML에 적용하는 세 가지 방법은 무엇일까요?`  

인라인 스타일: HTML 요소의 style 속성을 사용하여 직접 스타일을 정의하는 방법입니다.  

```<div style="color: red; font-size: 16px;">인라인 스타일</div>```  

내부 스타일 시트: HTML 문서 내에 <style> 태그를 사용하여 스타일을 정의하는 방법입니다.  

```<head>
    <style>
        div {
            color: red;
            font-size: 16px;
        }
    </style>
</head>
```

외부 스타일 시트: 별도의 CSS 파일을 생성하고 HTML 문서에서 링크하여 스타일을 적용하는 방법입니다.

```<head>
    <link rel="stylesheet" type="text/css" href="styles.css">
</head>
```
___

  `* 세 가지 방법 각각의 장단점은 무엇일까요?`  
  
인라인 스타일: 적용 범위가 제한적이며, 유지보수가 어렵습니다. 그러나 우선순위가 가장 높습니다.  

내부 스타일 시트: HTML 문서 내에서 스타일을 관리할 수 있으며, 적용 범위가 인라인보다는 넓습니다.  

외부 스타일 시트: 스타일을 별도의 파일로 분리하여 관리할 수 있으며, 여러 HTML 문서에서 동일한 스타일을 사용할 수 있습니다. 유지보수와 캐시 이점이 있습니다.  
___
`* CSS 규칙의 우선순위는 어떻게 결정될까요?`  

!important: !important로 지정된 속성은 모든 다른 우선순위를 무시하고 적용됩니다.  

인라인 스타일: HTML 요소에 직접 적용된 인라인 스타일은 가장 높은 우선순위를 가집니다.  

내부 스타일 시트: <style> 태그 내에서 정의된 스타일은 인라인 스타일보다 우선시됩니다.  

외부 스타일 시트: 외부 CSS 파일에 정의된 스타일은 가장 낮은 우선순위를 가집니다.  

`* CSS의 박스모델은 무엇일까요? 박스가 화면에서 차지하는 크기는 어떻게 결정될까요?`  

콘텐츠: 요소에 포함된 텍스트나 이미지 등의 실제 내용입니다.  

패딩: 콘텐츠와 테두리 사이의 공간입니다.  

테두리: 콘텐츠를 감싸는 테두리의 두께입니다.  

마진: 요소와 주변 요소 사이의 공간입니다.
___

`* float 속성은 왜 좋지 않을까요?`  

레이아웃 충돌: float 요소가 상위 요소의 높이를 고려하지 않고 부동하기 때문에 레이아웃이 충돌할 수 있습니다.  

컨테이너의 높이 결정: float된 요소들이 컨테이너의 높이를 결정하지 않아서 부모 요소의 높이를 잃어버릴 수 있습니다.  

응답성: float된 요소들은 반응형 디자인과 같은 동적인 레이아웃을 만들기에 적합하지 않을 수 있습니다.
___

`* Flexbox(Flexible box)와 CSS Grid의 차이와 장단점은 무엇일까요?`  

Flexbox:  

단일 차원 레이아웃: 주로 한 줄 또는 한 열로 요소를 배치하는 데 사용됩니다.
요소 간 공간 분배: 요소 사이의 공간 분배를 유연하게 제어할 수 있습니다.
컨텐츠 정렬: 요소를 수평 또는 수직으로 정렬할 수 있습니다.
단순한 구현: 단일 차원에서의 레이아웃을 쉽게 구현할 수 있습니다.  

CSS Grid:  

이차원 그리드: 행과 열을 모두 고려하여 요소를 배치하는 데 사용됩니다.
복잡한 레이아웃: 복잡한 그리드 레이아웃을 만들 수 있습니다.
간격 조절: 행과 열의 간격을 조절할 수 있습니다.
아이템 정렬: 그리드 영역 내에서 아이템의 배치와 정렬을 제어할 수 있습니다.

___

`* CSS의 비슷한 요소들을 어떤 식으로 정리할 수 있을까요?`  

CSS의 비슷한 요소들을 정리하는 방법은 다양합니다. 일반적으로 비슷한 기능을 갖는 속성들을 그룹화하여 정리하거나 주석을 사용하여 각 그룹을 설명하는 방법을 선택할 수 있습니다.  

예를 들어, 다음과 같은 방법으로 CSS 속성들을 정리할 수 있습니다:  

```/* 텍스트 관련 속성 */
p {
    font-family: Arial, sans-serif;
    font-size: 16px;
    line-height: 1.5;
    color: #333;
}

/* 배경 관련 속성 */
div {
    background-color: #f0f0f0;
    border: 1px solid #ccc;
    border-radius: 5px;
    box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.1);
}

/* 레이아웃 관련 속성 */
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
}
```
___
## Quest
* Quest 01에서 만들었던 HTML을 바탕으로, [이 그림](screen.png)의 레이아웃과 CSS를 최대한 비슷하게 흉내내 보세요. 꼭 완벽히 정확할 필요는 없으나 align 등의 속성은 일치해야 합니다.
* **주의사항: 되도록이면 원래 페이지의 CSS를 참고하지 말고 아무것도 없는 백지에서 시작해 보도록 노력해 보세요!**

## Advanced
* 왜 CSS는 어려울까요?
* CSS의 어려움을 극복하기 위해 어떤 방법들이 제시되고 나왔을까요?
* CSS가 브라우저에 의해 해석되고 적용되기까지 내부적으로 어떤 과정을 거칠까요?
* 웹 폰트의 경우에는 브라우저 엔진 별로 어떤 과정을 통해 렌더링 될까요?
