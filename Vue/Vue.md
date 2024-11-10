# 개요
## SPA (Single Page Application)
단일 페이지에서 동작하는 웹 애플리케이션

## CSR (Client-Side Rendering)
클라이언트에서 콘텐츠를 렌더링하는 방식

### CSR 작동 예시
1. 클라이언트는 서버로부터 최소한의 HTML과 JavaScript 파일을 응답 받음
2. 클라이언트 측에서 JavaScript를 사용하여 DOM을 업데이트하고 페이지를 렌더링
3. 이후 서버는 더 이상 HTML을 제공하지 않고 요청에 필요한 데이터만 응답

## SPA와 CSR의 장단점
### 장점
1. 빠른 페이지 전환
2. 사용자 경험
3. Frontend와 Backend의 명확한 분리

### 단점
1. 느린 초기 로드 속도
2. SEO(검색 엔진 최적화) 문제

# Vue
사용자 인터페이스(UI)를 구축하기 위한 JavaScript 프레임워크

## 2가지 핵심 기능
1. ${\textsf{\color{orange}선언적 렌더링}}$
  - JavaScript 상태(데이터)를 기반으로 화면에 출력될 HTML을 선언적으로 작성
2. ${\textsf{\color{orange}반응성}}$
  - JavaScript 상태 변경을 추적하고, 변경사항이 발생하면 자동으로 DOM을 업데이트

## Component
- 재사용 가능한 코드 블록
- UI를 독립적이고 재사용 가능한 일부분으로 분할하고 각 부분을 개별적으로 다룰 수 있음

## ref()
- .value 속성이 있는 ref 객체로 래핑하여 반환하는 함수
- ref로 선언된 변수의 값이 변경되면, 해당 값을 사용하는 템플릿에서 자동으로 업데이트

## Template Syntax
1. **Text Interpolation**
```js
<p>Message: {{ msg }}</p>
```
- 해당 구성 요소 인스턴스의 msg 속성 값으로 대체
- msg 속성이 변경될 때마다 업데이트 됨

2. **Raw HTML**
```js
<div v-html="rawHTML"></div>
const rawHTML = ref('<span style="color:red">This should be red.</span>')
```
- 콧수염 구문은 일반 텍스트로 해석하기 때문에 실제 HTML을 출력하려면 **v-html**을 사용

3. **Attribute Bindings**
```js
<div v-bind:id="dynamicId"></div>
const dynamicId = ref('my-id')
```
- 콧수염 구문은 HTML 속성 내에서 사용할 수 없기 때문에 **v-bind**를 사용
- HTML의 id 속성 값을 vue의 dynamicId 속성과 동기화 되도록 함

4. **JavaScript Expressions**
- Vue는 모든 데이터 바인딩 내에서 **JavaScript 표현식**의 모든 기능을 지원
- 콧수염 구문 내부 / 모든 directive의 속성값