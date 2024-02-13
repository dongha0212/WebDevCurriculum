# Quest 03. 자바스크립트와 DOM

## Introduction
* 자바스크립트는 현재 웹 생태계의 근간인 프로그래밍 언어입니다. 이번 퀘스트에서는 자바스크립트의 기본적인 문법과, 자바스크립트를 통해 브라우저의 실제 DOM 노드를 조작하는 법에 대하여 알아볼 예정입니다.

## Topics
* 자바스크립트의 역사
* 기본 자바스크립트 문법
* DOM API
  * `document` 객체
  * `document.getElementById()`, `document.querySelector()`, `document.querySelectorAll()` 함수들
  * 기타 DOM 조작을 위한 함수와 속성들
* 변수의 스코프
  * `var`, `let`, `const`

## Resources
* [자바스크립트 첫걸음](https://developer.mozilla.org/ko/docs/Learn/JavaScript/First_steps)
* [자바스크립트 구성요소](https://developer.mozilla.org/ko/docs/Learn/JavaScript/Building_blocks)
* [Just JavaScript](https://justjavascript.com/)

## Checklist
`* 자바스크립트는 버전별로 어떻게 변화하고 발전해 왔을까요?`  

ES5 (ECMAScript 5):  

2009년에 발표되었습니다.  

대부분의 모던 웹 브라우저에서 지원되는 범용적인 JavaScript 표준입니다.  

기존의 JavaScript 기능을 개선하고 몇 가지 새로운 기능을 도입했습니다.  

ES6 (ECMAScript 2015):  

2015년에 발표되었습니다.  

대규모 업데이트로, 많은 새로운 기능과 문법이 추가되었습니다.  

화살표 함수, 템플릿 리터럴, 클래스, let 및 const 키워드 등의 새로운 기능이 도입되었습니다.  

ES2016, ES2017, ... (ECMAScript 2016, 2017, ...):  
  
2016년과 2017년에는 작은 변경 사항을 포함한 빠른 연속된 릴리스가 있었습니다.  

예를 들어, ES2016에는 배열의 지수 연산자가 추가되었고, ES2017에는 async/await와 같은 비동기 프로그래밍을 위한 기능이 추가되었습니다.  

___

 `* 자바스크립트의 버전들을 가리키는 ES5, ES6, ES2016, ES2017 등은 무엇을 이야기할까요?`  
 ES5, ES6, ES2016, ES2017 등은 ECMAScript의 년도별 버전을 가리키며, 이들은 ECMAScript 언어의 표준을 정의하는 기술 위원회인 ECMA International에 의해 관리됩니다.   
___
  
`* 자바스크립트의 표준은 어떻게 제정될까요?`  

자바스크립트의 표준은 ECMA International에서 제정됩니다.  

ECMAScript의 표준화 프로세스는 다음과 같은 단계를 거칩니다:  

제안(Proposal): 새로운 기능 또는 변경 사항에 대한 제안이 ECMA TC39(Technical Committee 39)라고 불리는 ECMAScript 표준 위원회에 의해 제출됩니다.  

신뢰성 및 효용성 검토: 제안된 변경 사항이 신뢰성과 효용성을 갖추었는지에 대한 검토가 이루어집니다.   
이 단계에서는 여러 가지 관련된 요소들을 고려하여 제안이 승인되거나 거절됩니다.  

채택(Adoption): 제안이 최종적으로 ECMA 표준으로 채택됩니다. 이 때, 채택된 사양은 ECMAScript의 새로운 버전으로 포함됩니다.  

구현(Implementation): 표준으로 채택된 사양은 다양한 자바스크립트 엔진 개발자들에 의해 구현되어 실제로 사용됩니다.  

테스트(Test): 표준 사양의 구현이 테스트되고 검증되어 호환성과 안정성을 보장합니다.

___
  
`* 자바스크립트의 문법은 다른 언어들과 비교해 어떤 특징이 있을까요?`  

동적 타입 언어(Dynamically Typed Language):  

자바스크립트는 변수의 데이터 타입을 명시적으로 선언하지 않고도 사용할 수 있는 동적 타입 언어입니다.   
이는 변수가 실행 시간(runtime)에 자동으로 타입이 결정되며, 동적으로 타입이 변경될 수 있음을 의미합니다.  

함수형 프로그래밍 지원(Functional Programming Support):  

자바스크립트는 함수를 일급 객체로 취급하고, 고차 함수(higher-order function), 클로저(closure), 익명 함수(anonymous function) 등의 함수형 프로그래밍 개념을 지원합니다.  

객체 기반(Object-Based):  

자바스크립트는 객체 지향 프로그래밍 언어이며, 객체 기반의 특성을 가지고 있습니다. 모든 것이 객체이며, 프로토타입 기반 상속(Prototype-based Inheritance)을 사용합니다.  

이벤트 기반 프로그래밍(Event-driven Programming):  

자바스크립트는 이벤트 기반 프로그래밍 모델을 채택하여 비동기적으로 이벤트에 응답하고 처리할 수 있습니다. 이는 웹 애플리케이션의 상호작용성을 향상시키는 데 중요한 역할을 합니다.  

클라이언트 측 스크립팅 언어(Client-side Scripting Language):  

자바스크립트는 주로 웹 브라우저에서 사용되는 클라이언트 측 스크립팅 언어로 알려져 있습니다.   
이는 HTML과 함께 사용되어 웹 페이지의 동적인 동작을 제어하고 사용자 인터랙션을 처리하는 데 사용됩니다.  

자유로운 문법(Flexible Syntax):  


자바스크립트의 문법은 다른 언어들에 비해 상당히 유연합니다. 세미콜론의 생략이 가능하고, 중괄호의 사용이 자유로우며, 변수 선언에 var, let, const 등 다양한 키워드를 사용할 수 있습니다.  

___

`* 자바스크립트에서 반복문을 돌리는 방법은 어떤 것들이 있을까요?`  

for 문:  

가장 일반적인 반복문으로, 지정된 횟수만큼 반복합니다.

```for (let i = 0; i < 5; i++) {
    console.log(i);
}
```
while 문:  

주어진 조건이 true인 동안 반복합니다.  

```let i = 0;
while (i < 5) {
    console.log(i);
    i++;
}
```

do-while 문:  

먼저 코드를 실행하고, 그 후에 조건을 확인하여 반복 여부를 결정합니다.  

```let i = 0;
do {
    console.log(i);
    i++;
} while (i < 5);
```
for...in 문:  

객체의 열거 가능한 속성을 반복합니다.  

```const person = { name: 'John', age: 30 };
for (const key in person) {
    console.log(key + ': ' + person[key]);
}
```
이러한 반복문들은 각각의 상황에 맞게 선택하여 사용할 수 있습니다.   
일반적으로 배열을 반복할 때는 for...of 문을 사용하고, 객체의 속성을 반복할 때는 for...in 문을 사용하는 것이 일반적입니다.  
그 외의 상황에서는 for 문이나 while 문을 활용하여 반복문을 작성할 수 있습니다.

___

`* 자바스크립트를 통해 DOM 객체에 CSS Class를 주거나 없애려면 어떻게 해야 하나요?`  

classList 프로퍼티를 사용하여 클래스 추가/제거:  

classList 프로퍼티를 사용하면 요소의 클래스 목록을 조작할 수 있습니다.   
add() 메서드를 사용하여 클래스를 추가하고 remove() 메서드를 사용하여 클래스를 제거할 수 있습니다.  

```// 클래스 추가
document.getElementById("myElement").classList.add("newClass");

// 클래스 제거
document.getElementById("myElement").classList.remove("oldClass");
```
className 프로퍼티를 사용하여 클래스 전체를 설정:  

className 프로퍼티를 사용하면 요소의 클래스를 전체적으로 설정할 수 있습니다. 이 방법은 클래스를 한 번에 설정하는 데 유용합니다.  

```// 클래스 설정 (기존 클래스는 덮어쓰기 됨)
document.getElementById("myElement").className = "newClass";
```
classList.toggle() 메서드를 사용하여 클래스 추가/제거 토글:  

toggle() 메서드를 사용하면 클래스를 추가하거나 제거할 수 있습니다.  
만약 해당 클래스가 이미 존재한다면 제거하고, 존재하지 않는다면 추가합니다.  

```
// 클래스 추가 또는 제거 토글
document.getElementById("myElement").classList.toggle("active");
```

myElement 는 요소의 id이며, newClass 및 oldClass 는 추가하거나 제거할 클래스 이름입니다.

___

`* IE9나 그 이전의 옛날 브라우저들에서는 어떻게 해야 하나요?`  

className 프로퍼티를 사용하여 클래스 전체를 설정:  

className 프로퍼티를 사용하여 요소의 클래스를 전체적으로 설정합니다. 이 방법은 클래스를 한 번에 설정하는 데 사용됩니다.  

```// 클래스 추가
var element = document.getElementById("myElement");
element.className += " newClass";

// 클래스 제거
var element = document.getElementById("myElement");
element.className = element.className.replace("oldClass", "").trim();
```
getAttribute() 및 setAttribute() 메서드를 사용하여 클래스 조작:  

getAttribute() 메서드로 클래스를 가져오고, setAttribute() 메서드로 클래스를 설정합니다. 이 방법은 클래스를 개별적으로 조작할 수 있습니다.  

```// 클래스 추가
var element = document.getElementById("myElement");
var classes = element.getAttribute("class");
classes += " newClass";
element.setAttribute("class", classes);

// 클래스 제거
var element = document.getElementById("myElement");
var classes = element.getAttribute("class");
classes = classes.replace("oldClass", "").trim();
element.setAttribute("class", classes);
```
위의 예제에서 myElement는 요소의 id이며, newClass 및 oldClass 는 추가하거나 제거할 클래스 이름입니다.

___

  
`* 자바스크립트의 변수가 유효한 범위는 어떻게 결정되나요?`  

전역 스코프(Global Scope):  

전역 범위에서 선언된 변수는 스크립트 어디에서나 접근할 수 있습니다.  

```var globalVar = 10;

function foo() {
    console.log(globalVar); // 전역 변수에 접근 가능
}
foo(); // 출력: 10
```
지역 스코프(Local Scope):  

함수 내부에서 선언된 변수는 해당 함수 내부에서만 접근할 수 있습니다.  

```function foo() {
    var localVar = 20;
    console.log(localVar); // 함수 내부에서 선언된 지역 변수에 접근 가능
}
foo(); // 출력: 20
console.log(localVar); // 에러: localVar는 함수 외부에서 접근할 수 없음
```

블록 스코프(Block Scope):  

ES6(ES2015)부터 let과 const 키워드를 사용하여 블록 스코프를 생성할 수 있습니다.   
블록 스코프는 {}로 둘러싸인 코드 블록 내에서만 변수가 유효합니다.  

```if (true) {
    let blockVar = 30;
    console.log(blockVar); // 블록 내부에서 선언된 블록 변수에 접근 가능
}
console.log(blockVar); // 에러: blockVar는 블록 외부에서 접근할 수 없음
```
함수 매개변수 스코프(Function Parameter Scope):  

함수의 매개변수는 함수 내부에서만 유효한 지역 변수로 취급됩니다.  

```function foo(param) {
    console.log(param); // 함수 내부에서 선언된 매개변수에 접근 가능
}
foo(40); // 출력: 40
```
변수의 스코프는 변수가 선언된 위치에 따라 동적으로 결정되며,   
스코프 체인(Scope Chain)을 통해 변수가 접근 가능한지 여부가 결정됩니다.   
스코프 체인은 변수를 찾을 때, 현재 스코프부터 외부 스코프로 이동하면서 변수를 검색하는 메커니즘입니다. 

___

`* var과 let으로 변수를 정의하는 방법들은 어떻게 다르게 동작하나요?`  

변수의 유효 범위(Scope):  

var: 함수 스코프(Function Scope)를 갖습니다.   
즉, 함수 내에서 선언된 변수는 함수 내부에서만 유효하며 함수 외부에서는 접근할 수 없습니다.  

let: 블록 스코프(Block Scope)를 갖습니다.   
즉, {}로 둘러싸인 코드 블록 내에서만 변수가 유효하며 블록 외부에서는 접근할 수 없습니다. 

변수의 재선언(Re-declaration):  

var: 같은 변수 이름으로 여러 번 선언해도 에러가 발생하지 않고, 이전에 선언된 변수를 덮어씁니다.  

let: 같은 변수 이름으로 다시 선언하면 SyntaxError가 발생합니다.  

변수의 호이스팅(Hoisting):  

var: 변수 선언이 해당 스코프의 최상단으로 끌어올려지는 현상이 발생합니다.   
그러나 변수의 할당은 원래 선언된 위치에 남아 있습니다.   

let: 변수 선언은 호이스팅되지만, 초기화되지 않습니다.   
따라서 선언된 변수를 초기화하기 전에 접근하면 ReferenceError가 발생합니다.  

전역 객체와의 관계:  

var: 전역 객체(window 객체 또는 global 객체)의 프로퍼티로 선언됩니다.  

let: 전역 객체와의 관계가 없습니다. 블록 스코프 내에서만 유효합니다.  

```function example() {
    if (true) {
        var varVariable = 'var';
        let letVariable = 'let';
    }
    console.log(varVariable); // 'var'
    console.log(letVariable); // ReferenceError: letVariable is not defined
}
example();

console.log(varVariable); // 'var'
console.log(letVariable); // ReferenceError: letVariable is not defined

var varVariable = 'var';
var varVariable = 'var2'; // 재선언에 대한 에러 없음

let letVariable = 'let';
let letVariable = 'let2'; // SyntaxError: Identifier 'letVariable' has already been declared
```
요약하면, let은 블록 스코프를 갖고 변수의 재선언이 허용되지 않으며, 호이스팅 시 초기화되지 않습니다.   
반면에 var는 함수 스코프를 갖고 재선언이 허용되며, 호이스팅 시 초기화됩니다. 

___


`* 자바스크립트의 익명 함수는 무엇인가요?`  

자바스크립트에서 익명 함수(Anonymous Function)는 이름이 없는 함수를 의미합니다.   
즉, 함수를 선언할 때 함수의 이름을 생략한 형태를 말합니다.  

`* 자바스크립트의 Arrow function은 무엇일까요?`  

JavaScript의 Arrow function(화살표 함수)은 ES6(ES2015)에서 도입된 새로운 함수 선언 방식입니다.  
Arrow function은 보다 간결하고 간편한 문법을 제공하며, 함수를 정의하는 데 사용됩니다.  


Arrow function의 주요 특징은 다음과 같습니다:  

간결한 문법:  

Arrow function은 더 간결한 문법을 제공하여 함수를 더 간편하게 정의할 수 있습니다.  

중괄호 생략:   

함수의 몸체가 한 줄인 경우 중괄호 {}를 생략할 수 있습니다.  

암묵적인 반환:  

함수의 몸체가 한 줄인 경우, return 키워드를 사용하지 않고도 암묵적으로 값을 반환합니다.  

Lexical this:  

Arrow function은 자신의 this를 바인딩하지 않고, 주변 스코프의 this를 그대로 사용합니다.   
이를 Lexical this라고 합니다.  

```// 기본 문법
const myFunction = () => {
    // 함수 본문
};

// 매개변수가 있는 경우
const add = (a, b) => {
    return a + b;
};

// 매개변수가 하나인 경우 소괄호를 생략할 수 있음
const square = num => num * num;

// 몸체가 한 줄인 경우 중괄호와 return 문을 생략할 수 있음
const double = num => num * 2;
```
Arrow function은 this를 바인딩하지 않기 때문에 메소드로 사용할 때 주의해야 합니다.
  
## Quest
* (Quest 03-1) 초보 프로그래머의 영원한 친구, 별찍기 프로그램입니다.
  * [이 그림](jsStars.png)과 같이, 입력한 숫자만큼 삼각형 모양으로 콘솔에 별을 그리는 퀘스트 입니다.
    * 줄 수를 입력받고 그 줄 수만큼 별을 그리면 됩니다. 위의 그림은 5를 입력받았을 때의 결과입니다.
  * `if`와 `for`와 `function`을 다양하게 써서 프로그래밍 하면 더 좋은 코드가 나올 수 있을까요?
  * 입력은 `prompt()` 함수를 통해 받을 수 있습니다.
  * 출력은 `console.log()` 함수를 통해 할 수 있습니다.
* (Quest 03-2) skeleton 디렉토리에 주어진 HTML을 조작하는 스크립트를 완성해 보세요.
  * 첫째 줄에 있는 사각형의 박스들을 클릭할 때마다 배경색이 노란색↔흰색으로 토글되어야 합니다.
  * 둘째 줄에 있는 사각형의 박스들을 클릭할 때마다 `enabled`라는 이름의 CSS Class가 클릭된 DOM 노드에 추가되거나 제거되어야 합니다.
* 구현에는 여러 가지 방법이 있으나, 다른 곳은 건드리지 않고 TODO 부분만 고치는 방향으로 하시는 것을 권장해 드립니다.

## Advanced
* Quest 03-1의 코드를 더 구조화하고, 중복을 제거하고, 각각의 코드 블록이 한 가지 일을 전문적으로 잘하게 하려면 어떻게 해야 할까요?
* Quest 03-2의 스켈레톤 코드에서 `let` 대신 `var`로 바뀐다면 어떤 식으로 구현할 수 있을까요?
