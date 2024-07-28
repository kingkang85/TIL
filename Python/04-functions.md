# Functions
- 특정 작업을 수행하기 위한 ${\textsf{\color{blue}재사용 가능}}$한 코드 묶음
- ${\textsf{\color{blue}가독성과 유지보수성}}$ 향상

## 함수의 구조
### 함수 구조
- `input x` : 입력값
- `Docstring` : 함수 body 앞에 선택적으로 작성하는 함수 설명서
- `function body`
- `return f(x)` : 반환값
  - **return** 문은 함수의 실행을 종료하고, 결과를 호출 부분으로 반환
  - return을 쓰지 않으면 `None`을 반환


## 매개변수와 인자
- 매개변수 `parameter` : 함수를 **정의**할 때, 함수가 받을 값을 나타내는 변수
- 인자 `argument` : 함수를 **호출**할 때, 실제로 전달되는 값

## 인자 종류
### 1. 위치 인자 (Positional Arguments)
- 함수 호출 시 인자의 위치에 따라 전달되는 인자
- ${\textsf{\color{orange}위치 인자는 함수 호출 시 반드시 값을 전달}}$

### 2. 기본 인자 값 (Default Argument Values)
- 함수 **정의** 시 매개변수에 기본 값을 할당
- 함수 **호출** 시 인자를 전달하지 않으면, 기본 값이 매개변수에 할당

### 3. 키워드 인자 (Keyword Arguments)
- 함수 호출 시 인자의 이름과 함께 값을 전달
- ${\textsf{\color{orange}단, 위치 인자가 먼저!!!}}$

### 4. 임의의 인자 목록 (Arbitrary Argument Lists)
- 함수 **정의** 시 매개변수 앞에 `*`을 붙여 사용하며, 여러 개의 인자를 `tuple`로 처리

### 5. 임의의 키워드 인자 목록 (Arbitrary Keyword Argument Lists)
- 함수 **정의** 시 매개변수 앞에 `**`을 붙여 사용하며, 여러 개의 인자를 `dictionary`로 묶어 처리

## 재귀 함수
- 함수 내부에서 자기 자신을 호출하는 함수
