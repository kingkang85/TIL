# Django URLs
## 변수와 URL - Variable Routing
- URL 일부에 변수를 포함시키는 것
- 변수는 view 함수의 인자로 전달할 수 있음

### 작성법
<${\textsf{\color{crimson}path converter}}$:${\textsf{\color{blue}variable name}}$>

- Path converters
  - URL 변수의 타입을 지정

## App과 URL - App URL mapping
- 각 앱에 URL을 정의하는 것
- 프로젝트와 각 앱이 URL을 나누어 관리를 편하게 하기 위함

### include()
- 프로젝트 내부 앱들의 URL을 참조할 수 있도록 매핑하는 함수

## URL 이름 지정
- URL에 이름을 지정하는 것
- path 함수의 name 인자를 정의해서 사용

## URL 이름 공간
- URL 이름 지정 후 남은 문제
  - 두 앱의 url 이름이 같다면? 어떤 경로로 요청을 보내야할 지 알 수 없음
- ${\textsf{\color{orange}'app\_name' 속성}}$을 지정하여 해결