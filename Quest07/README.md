# Quest 07. node.js의 기초

## Introduction
* 이번 퀘스트에서는 node.js의 기본적인 구조와 개념에 대해 알아 보겠습니다.

## Topics
* node.js
* npm
* CommonJS와 ES Modules

## Resources
* [About node.js](https://nodejs.org/ko/about/)
* [Node.js의 아키텍쳐](https://edu.goorm.io/learn/lecture/557/%ED%95%9C-%EB%88%88%EC%97%90-%EB%81%9D%EB%82%B4%EB%8A%94-node-js/lesson/174356/node-js%EC%9D%98-%EC%95%84%ED%82%A4%ED%85%8D%EC%B3%90)
* [npm](https://docs.npmjs.com/about-npm)
* [npm CLI commands](https://docs.npmjs.com/cli/v7/commands)
* [npm - package.json](https://docs.npmjs.com/cli/v7/configuring-npm/package-json)
* [How NodeJS Require works!](https://www.thirdrocktechkno.com/blog/how-nodejs-require-works)
* [MDN - JavaScript Modules](https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Modules)
* [ES modules: A cartoon deep-dive](https://hacks.mozilla.org/2018/03/es-modules-a-cartoon-deep-dive/)
* [require vs import](https://www.geeksforgeeks.org/difference-between-node-js-require-and-es6-import-and-export/)

## Checklist
`* node.js는 무엇인가요? node.js의 내부는 어떻게 구성되어 있을까요?`  

Node.js는 Chrome V8 JavaScript 엔진으로 빌드된 JavaScript 런타임 환경입니다.  
Node.js는 브라우저 환경이 아닌 서버 측 JavaScript 프로그래밍을 가능하게 합니다.   
주요 특징으로는 비동기 이벤트 기반의 입출력 모델을 사용하여 높은 성능과 확장성을 제공하며,   
자바스크립트를 사용하여 서버 측 애플리케이션을 개발할 수 있도록 합니다.  

Node.js의 내부 구성은 다음과 같은 요소들로 이루어져 있습니다:  

1. v8 엔진
2. Libuv 라이브러리
3. 코어 모듈
4. 내장 HTTP 서버
5. 패키지 매니저

___

`* npm이 무엇인가요? package.json 파일은 어떤 필드들로 구성되어 있나요?`  

npm은 Node Package Manager의 약자로, JavaScript 프로그램을 위한 패키지 관리 도구입니다.   

npm은 JavaScript 프로젝트에서 필요한 패키지(라이브러리)를 검색하고 설치하며, 프로젝트에 종속성을 관리하는 데 사용됩니다.   


Node.js를 설치하면 npm도 함께 설치됩니다.  


일반적으로 package.json 파일은 다음과 같은 필드로 구성됩니다:  


name: 프로젝트의 이름을 나타내는 문자열입니다. 이 이름은 npm 레지스트리에서 해당 패키지를 식별하는 데 사용됩니다.  


version: 프로젝트의 현재 버전을 나타내는 문자열입니다. 일반적으로 Semantic Versioning (SemVer) 규칙을 따릅니다.  


description: 프로젝트에 대한 간단한 설명을 제공하는 문자열입니다.  

 
main: 프로젝트의 주 진입점 파일을 나타내는 문자열입니다. 보통 이 파일은 모듈의 진입점이며, 다른 모듈들에서 require() 함수를 사용하여 불러올 때 사용됩니다.  


scripts: 프로젝트에서 사용할 수 있는 사용자 정의 스크립트를 정의하는 객체입니다. 이 필드를 통해 테스트, 빌드, 실행 및 기타 작업을 자동화할 수 있습니다.  


dependencies: 프로젝트가 종속하는 패키지들을 나타내는 객체입니다. 이 필드에는 패키지 이름과 해당 버전이 포함됩니다.  


devDependencies: 개발 중에만 필요한 패키지들을 나타내는 객체입니다. 일반적으로 테스트, 빌드, 문서 생성 등의 작업을 위한 도구들이 여기에 포함됩니다.  


keywords: 프로젝트와 관련된 키워드들을 나타내는 배열입니다. 이 키워드들은 npm 레지스트리에서 프로젝트를 검색할 때 사용될 수 있습니다.  


author: 프로젝트의 저자를 나타내는 문자열이나 객체입니다.  


license: 프로젝트의 라이센스 정보를 나타내는 문자열입니다.  

___



`* npx는 어떤 명령인가요? npm 패키지를 `-g` 옵션을 통해 글로벌로 저장하는 것과 그렇지 않은 것은 어떻게 다른가요?`  

npx는 npm 패키지를 실행하는 데 사용되는 도구입니다.  

일반적으로 npm 패키지를 실행하려면 해당 패키지를 글로벌로 설치해야 합니다.   

그러나 npx를 사용하면 로컬로 설치된 패키지 또는 npm 레지스트리에서 다운로드한 패키지를 즉시 실행할 수 있습니다.  

npm 패키지를 -g 옵션을 통해 글로벌로 설치하는 것과 그렇지 않은 것은 몇 가지 차이점이 있습니다:  


접근성: 글로벌로 설치된 패키지는 시스템 전체에서 접근할 수 있습니다.   

이는 해당 패키지를 여러 프로젝트에서 사용할 수 있다는 장점이 있지만,  

시스템에 영구적으로 설치되므로 여러 버전의 패키지를 유지하기가 어려울 수 있습니다.  

프로젝트 별 의존성 관리: 프로젝트마다 패키지의 의존성 버전을 다르게 관리할 수 있습니다.   

글로벌로 설치된 패키지는 모든 프로젝트에서 동일한 버전을 사용해야 하지만,   

로컬로 설치된 패키지는 각 프로젝트에 따라 의존성 버전을 독립적으로 관리할 수 있습니다.  

프로젝트 이전성: 프로젝트의 이전성이 증가합니다.   

프로젝트의 의존성을 package.json 파일에 명시하여 다른 개발자들이 프로젝트를 쉽게 설정하고 실행할 수 있습니다.  

___

`* 자바스크립트 코드에서 다른 파일의 코드를 부르는 시도들은 지금까지 어떤 것이 있었을까요? CommonJS 대신 ES Modules가 등장한 이유는 무엇일까요?`  

자바스크립트 코드에서 다른 파일의 코드를 불러오는 시도들은 몇 가지가 있었습니다.   

가장 널리 사용되는 것은 CommonJS와 AMD(Asynchronous Module Definition)입니다.  

ES Modules가 등장한 이유는 다음과 같습니다:  


표준화: ES Modules는 자바스크립트 언어 자체의 일부로 표준화되었습니다.   

이는 브라우저, Node.js 및 다른 자바스크립트 환경에서 일관된 모듈 시스템을 제공하며, 이를 통해 개발자들은 여러 환경에서 동일한 코드를 사용할 수 있습니다.  

정적 분석: ES Modules는 정적 분석이 가능하므로 더 나은 성능 최적화와 도구 지원을 제공합니다.   

이는 브라우저가 페이지 로드 시에 모듈을 사전에 파악하고 필요한 모듈만 미리 로드하여 초기 로딩 속도를 개선할 수 있도록 합니다.  

브라우저 내장 지원: 최신 브라우저는 ES Modules를 기본적으로 지원하므로 별도의 라이브러리나 로더를 사용하지 않고도 모듈을 사용할 수 있습니다.  

동적 로딩: ES Modules는 비동기적으로 모듈을 로드할 수 있는 기능을 제공합니다. 이는 필요한 모듈을 동적으로 로드하여 애플리케이션의 성능을 향상시킬 수 있습니다.  

___

`* ES Modules는 기존의 `require()`와 동작상에 어떤 차이가 있을까요? CommonJS는 할 수 있으나 ES Modules가 할 수 없는 일에는 어떤 것이 있을까요?`  

1. 정적 vs. 동적 로딩
2. Top-level scope
3. 동적 이름으로 모듈 불러오기
4. 노출되는 속성
   
CommonJS는 할 수 있으나 ES Modules가 할 수 없는 일 :  

동적 로딩의 유연성:  

CommonJS: CommonJS는 require() 함수를 사용하여 모듈을 동적으로 로드할 수 있습니다. 이는 프로그램이 실행되는 동안 필요한 시점에 모듈을 로드할 수 있도록 합니다.  

ES Modules: ES Modules는 정적으로 모듈을 로드합니다. 즉, import 문은 프로그램의 상단에 있어야 하며, 런타임 중에 동적으로 모듈을 로드할 수 없습니다.  

동적 모듈 경로:  

CommonJS: CommonJS에서는 모듈 경로를 동적으로 생성할 수 있습니다.   

즉, require() 함수에 문자열이 아닌 변수나 표현식을 전달하여 모듈을 동적으로 결정할 수 있습니다.  

ES Modules: ES Modules에서는 import 문은 정적으로 모듈 경로를 해석합니다.  

따라서 모듈 경로는 문자열 리터럴로만 사용할 수 있으며, 동적으로 결정할 수 없습니다.  

동적으로 모듈을 노출하는 것:

CommonJS: CommonJS에서는 exports 객체에 동적으로 속성을 추가하여 모듈이 동적으로 변경되고 노출될 수 있습니다.  

ES Modules: ES Modules에서는 모듈의 내보내기는 정적으로 이루어집니다.   

즉, 모듈의 내보내기는 모듈의 상단에 있어야 하며, 런타임 중에 동적으로 변경될 수 없습니다.  

실행 컨텍스트:  

CommonJS: CommonJS 모듈은 모듈이 로드될 때 실행되는 즉시 실행 함수(IIFE, Immediately Invoked Function Expression)의 형태를 취합니다.  

이는 모듈이 로드되고 초기화될 때마다 새로운 실행 컨텍스트가 생성됩니다.  

ES Modules: ES Modules는 기본적으로 상단 레벨에 정의되며, 모듈을 로드할 때 즉시 실행되지 않습니다.   

따라서 모듈의 내용은 실행 컨텍스트가 생성되기 전까지 실행되지 않습니다.

___

`* node.js에서 ES Modules를 사용하려면 어떻게 해야 할까요? ES Modules 기반의 코드에서 CommonJS 기반의 패키지를 불러오려면 어떻게 해야 할까요? 그 반대는 어떻게 될까요?`  

Node.js 버전 확인: 먼저 Node.js 버전이 12버전 이상이어야 합니다.   

ES Modules는 Node.js 12버전부터 실험적으로 지원되었으며, 14버전부터는 안정화되었습니다.   

따라서 가능하면 Node.js의 최신 버전을 사용하는 것이 좋습니다.  

파일 확장자 .mjs 사용: ES Modules를 사용하는 파일의 확장자를 .mjs로 지정해야 합니다.  

일반적으로 .js 확장자를 사용하는 파일은 CommonJS 모듈로 간주되므로, ES Modules를 사용하기 위해서는 파일 확장자를 변경해야 합니다.  

package.json 설정 변경(Optional): package.json 파일의 "type" 필드를 "module"으로 설정하여 프로젝트 전체에서 ES Modules를 사용하도록 지정할 수 있습니다.   

이렇게 설정하면 확장자를 .mjs로 지정하지 않고도 모든 .js 파일이 ES Modules로 간주됩니다.  


ES Modules 기반의 코드에서 CommonJS 기반의 패키지를 불러오려면 몇 가지 접근 방법이 있습니다.  

이를 위해서는 ES Modules가 지원하는 "named exports"를 사용하여 CommonJS 패키지를 가져와야 합니다.  

아래는 일반적인 방법입니다:  

CommonJS 패키지를 가져오기:

일반적으로 CommonJS 패키지는 require() 함수를 통해 불러옵니다.   

따라서 ES Modules에서 CommonJS 패키지를 불러올 때에도 require() 함수를 사용해야 합니다.  

```// ES Modules 파일
const commonJsPackage = require('common-js-package');
```
ES Modules로 내보내기:  

CommonJS 패키지를 ES Modules에서 사용할 수 있도록 내보내기 위해,   

해당 패키지가 ES Modules로 작성된 패키지이거나, CommonJS 패키지를 ES Modules 형식으로 래핑하여 내보낼 수 있습니다.   

이를 위해 일반적으로 다음과 같이 하나의 ES Modules 파일을 만듭니다:  

```// commonjsWrapper.mjs
import * as commonJsPackage from 'common-js-package';
export default commonJsPackage;
```

```// commonjsWrapper.mjs
import * as commonJsPackage from 'common-js-package';
export default commonJsPackage;
```

그런 다음, ES Modules 파일에서 이러한 패키지를 가져와 사용할 수 있습니다.

```// ES Modules 파일
import commonJsPackage from './commonjsWrapper.mjs';
```

default 속성 사용:  

일부 CommonJS 패키지는 module.exports 대신 exports.default를 사용하여 기본값을 내보낼 수 있습니다.   

이러한 패키지는 ES Modules에서 기본적으로 불러올 수 있습니다.  

```// CommonJS 패키지 내
module.exports.default = someValue;
```

```// ES Modules 파일
import someValue from 'common-js-package';
```

그 반대의 경우 :  

commonjsWrapper.mjs와 같은 ES Modules 파일을 생성하여 CommonJS 패키지를 내보냅니다.  

```// commonjsWrapper.mjs
import * as commonJsPackage from 'common-js-package';
export default commonJsPackage;
```
이 파일을 ES Modules에서 불러와 사용합니다.  

```// ES Modules 파일
import commonJsPackage from './commonjsWrapper.mjs';
```

___

## Quest
* 스켈레톤 코드에는 다음과 같은 네 개의 패키지가 있으며, 용도는 다음과 같습니다:
  * `cjs-package`: CommonJS 기반의 패키지입니다. 다른 코드가 이 패키지의 함수와 내용을 참조하게 됩니다.
  * `esm-package`: ES Modules 기반의 패키지입니다. 다른 코드가 이 패키지의 함수와 내용을 참조하게 됩니다.
  * `cjs-my-project`: `cjs-package`와 `esm-package`에 모두 의존하는, CommonJS 기반의 프로젝트입니다.
  * `esm-my-project`: `cjs-package`와 `esm-package`에 모두 의존하는, ES Modules 기반의 프로젝트입니다.
* 각각의 패키지의 `package.json`과 `index.js` 또는 `index.mjs` 파일을 수정하여, 각각의 `*-my-project`들이 `*-package`에 노출된 함수와 클래스를 활용할 수 있도록 만들어 보세요.

## Advanced
* node.js 외의 자바스크립트 런타임에는 어떤 것이 있을까요?
