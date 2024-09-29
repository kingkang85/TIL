# DTL (Django Template Language)
- Template에서 조건, 반복, 변수 등의 프로그래밍적 기능을 제공하는 시스템

## DTL Syntax
### 1. Variable
  - render 함수의 세번째 인자로 딕셔너리 데이터를 사용
  - '.'을 사용하여 변수 속성에 접근 가능

### 2. Filters
  - 표시할 변수를 수정할 때 사용 (변수 + '|' + 필터)
  - chained(연결)이 가능하며 일부 필터는 인자를 받기도 함

### 3. Tags
  - 반복 또는 논리를 수행하여 제어 흐름을 만듦
  - 일부 태그는 시작과 종료 태그가 필요

### 4. Comments
  - DTL에서의 주석

## 템플릿 상속
- ${\textsf{\color{orange}페이지의 공통요소를 포함}}$하고, ${\textsf{\color{orange}하위 템플릿이 재정의 할 수 있는 공간}}$을 정의하는 기본 'skeleton' 템플릿을 작성하여 상속 구조를 구축
1. 상위 템플릿 (base.html) 작성
2. 기존 하위 템플릿 수정

### 상속 관련 DTL 태그
- `{% extends '...'}`
  - 자식 템플릿이 부모 템플릿을 확장한다는 것을 알림

- `{% block ... %}{% endblock ... %}`
  - 하위 템플릿에서 재정의 할 수 있는 블록을 정의