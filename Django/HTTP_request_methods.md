# HTTP request methods
- 데이터에 대해 수행을 원하는 작업을 나타내는 것
- 대표 메서드
  - GET, POST

## GET method
- 서버로부터 데이터를 요청하고 받아오는 데${\textsf{\color{crimson}(조회)}}$ 사용

### 특징
- URL의 쿼리 문자열을 통해 데이터를 전송
- URL 길이에 제한이 있어 대량의 데이터 전송에는 부적합
- 요청 URL이 브라우저 히스토리에 남음
- 캐싱
  - 브라우저는 GET 요청의 응답을 로컬에 저장할 수 있음
  - 동일한 URL로 다시 요청할 때, 서버에 접속하지 않고 저장된 결과를 사용
  - 페이지 로딩 시간을 크게 단축

## POST method
- 서버에 데이터를 제출하여 리소스를 ${\textsf{\color{crimson}변경(생성, 수정, 삭제)}}$ 하는 데 사용

### 특징
- HTTP Body를 통해 데이터를 전송
- GET에 비해 더 많은 양의 데이터 전송 가능
- POST 요청은 브라우저 히스토리에 남지 않음
- 캐싱
  - POST 요청은 기본적으로 캐시할 수 없음

### CSRF (Cross Site Request Forgery)
- 사이트 간 요청 위조<br>
⇒ 사용자가 자신의 의지와 무관하게 공격자가 의도한 행동을 하여 특정 웹 페이지를 보안에 취약하게 하거나 수정, 삭제 등의 작업을 하게 만드는 공격 방법

### CSRF Token 적용
- DTL의 csrf_token 태그 사용
  - `{% csrf_token %}`
- ${\textsf{\color{crimson}Django가 직접 제공한 페이지에서 데이터를 작성하고 있는 것인지}}$에 대한 확인이 필요

### Redirect
- redirect()
  - 클라이언트가 인자에 작성된 주소로 다시 요청을 보내도록 하는 함수