# HTML form
- HTTP 요청을 서버에 보내는 가장 편리한 방법

## 'form' element
- 사용자로부터 할당된 데이터를 서버로 전송
- 웹에서 사용자 정보를 입력하는 여러 방식 (text, password, checkbox 등)을 제공

### 핵심 속성 2가지
- **action**
  - 입력 데이터가 전송될 URL을 지정
  - 이 속성을 지정하지 않으면 현재 form이 있는 페이지의 URL로 보내짐

- **method**
  - 데이터를 어떤 방식으로 보낼 것인지 정의
  - 데이터의 HTTP request methods (GET, POST)를 지정

## 'input' element
- 사용자 데이터를 입력 받을 수 있는 요소

### 핵심 속성
- **name**
  - 사용자가 입력한 데이터에 붙이는 이름 (key)
  - 데이터를 제출했을 때 서버는 name 속성에 설정된 값을 통해서만 사용자가 입력한 데이터에 접근할 수 있음