# CSR (Client-Side Rendering)
클라이언트에서 콘텐츠를 렌더링 하는 방식

## 작동 예시
1. 클라이언트는 서버로부터 최소한의 HTML 페이지와 해당 페이지에 필요한 JavaScript 응답 받음
2. 클라이언트 측에서 JavaScript를 사용하여 DOM을 업데이트하고 페이지를 렌더링
3. 이후 서버는 더 이상 HTML을 제공하지 않고 요청에 필요한 데이터만 응답

⇒ Google Maps, Facebook, Instagram 등의 서비스에서 페이지 갱신 시 새로고침이 없는 이유

# Vue
사용자 인터페이스를 구축하기 위한 JavaScript 프레임워크

## Template Syntax
1. Text Interpolation
```js
<p>Message: {{ msg }}</p>
```
- 데이터 바인딩의 가장 기본적인 형태
- 이중 중괄호 구문을 사용
- 해당 구성 요소 인스턴스의 msg 속성 값으로 대체
- msg 속성이 변경될 때마다 업데이트 됨

2. Raw HTML
```js
<div v-html="rawHTML"></div>
const rawHTML = ref('<span style="color:red">This should be red.</span>')
```
- 콧수염 구문은 일반 텍스트로 해석하기 때문에 실제 HTML을 출력하려면 v-html을 사용

3. Attribute Bindings
```js
<div v-bind:id="dynamicId"></div>
const dynamicId = ref('my-id')
```
- 콧수염 구문은 HTML 속성 내에서 사용할 수 없기 때문에 v-bind를 사용
- HTML의 id 속성 값을 vuedml dynamicId 속성과 동기화 되도록 함

4. JavaScript Expressions
- Vue는 모든 데이터 바인딩 내에서 JavaScript 표현식의 모든 기능을 지원
- 콧수염 구문 내부 / 모든 directive의 속성값