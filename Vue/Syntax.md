# Directive
'v-' 접두사가 있는 특수 속성

## 특징
- 속성 값은 단일 JavaScript 표현식이어야 함 (v-for, v-on 제외)
- 표현식 값이 변경될 때 DOM에 반응적으로 업데이트를 적용

## 전체 구문
Name:Argument.Modifiers="Value"

### Arguments
일부 directive 뒤에 콜론(":")으로 표시되는 인자를 사용

### Modifiers
"."으로 표시되는 특수 접미사로, directive가 특별한 방식으로 바인딩되어야 함을 나타냄

## Built-in Directives
- v-text
- v-show
- v-if
- v-for
- ...

## v-bind
하나 이상의 속성 또는 컴포넌트 데이터를 표현식에 동적으로 바인딩(연결)

### Attribute Bindings
HTML 속성 값을 Vue의 상태 속성 값과 동기화 되도록 함
**Dynamic attribute name (동적 인자 이름)**
- 대괄호([])로 감싸서 directive argument에 JavaScript 표현식을 사용할 수 있음
- `<button :[key]="myValue"></button>`
- 대괄호 안에 작성하는 이름은 반드시 소문자로만 구성 가능

### Class and Style Bindings
1. Binding HTML Classes
1.1 Binding to Objects
1.2 Binding to Arrays

2. Binding Inline Styles
2.1 Binding to Objects
2.2 Binding to Arrays

## v-on
DOM 요소에 이벤트 리스너를 연결 및 수신
`v-on:event="handler"`
- 1. Inline handlers : 이벤트가 트리거될 때 실행될 JavaScirpt 코드
- 2. Method handlers : 컴포넌트에 정의된 메서드 이름

## Form Input Bindings
form을 처리할 때 사용자가 input에 입력하는 값을 실시간으로 JavaScript 상태에 동기화해야 하는 경우 (양방향 바인딩)

### v-bind와 v-on 함께 사용

### v-model 사용