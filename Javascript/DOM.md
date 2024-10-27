# DOM (The Document Object Model)
웹 페이지(Document)를 구조화된 객체로 제공하여 다른 프로그래밍 언어에서 접근하고 조작할 수 있는 방법을 제공

## document 객체
웹 페이지를 나타내는 DOM 트리의 최상위 객체<br>
⇒ HTML 문서의 모든 콘텐츠에 접근하고 조작할 수 있는 진입점

## DOM 선택
1. 조작 하고자 하는 요소를 ${\textsf{\color{crimson}선택}}$
2. 선택된 요소의 콘텐츠 또는 속성을 ${\textsf{\color{crimson}조작}}$

### 선택 메서드
`document.querySelector(selector)`
- 제공한 선택자와 일치하는 첫 번째 element 객체를 반환
  - 없다면 null 반환

`document.querySelectorAll(selector)`
- 제공한 선택자와 일치하는 NodeList를 반환

## DOM 조작
### 속성(attribute) 조작
  - 클래스 속성 조작
    - 'classList' property
    - 요소의 클래스 목록을 **DOMTokenList** 형태로 반환
    - classList 메서드
      - `element.classList.add()` : 지정한 클래스 값 추가
      - `element.classList.remove()` : 제거
      - `element.classList.toggle()` : 클래스가 존재하면 제거 후 false 반환, 존재하지 않으면 추가 후 true 반환
  
  - 일반 속성 조작
    - `Element.getAttribute()` : 해당 요소에 지정된 값을 반환 (조회)
    - `Element.setAttribute(name, value)` : 속성 값 설정, 이미 있으면 기존 값 갱신
    - `Element.removeAttribute()` : 속성 제거

### HTML 콘텐츠 조작
- 'textContent' property
- 요소의 텍스트 콘텐츠를 표현

### DOM 요소 조작
- `document.createElement(tagName)`
  - 작성한 tagName의 HTML 요소를 생성하여 반환
- `Node.appendChild()`
  - 특정 부모 노드의 자식 NodeList 중 마지막 자식으로 삽입
  - 추가된 Node 객체를 반환
- `Node.removeChild()`
  - DOM에서 자식 Node 제거
  - 제거된 노드를 반환

### style 조작
- 'style' property
- 해당 요소의 모든 style 속성 목록을 포함하는 속성
