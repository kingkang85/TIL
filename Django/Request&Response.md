# Django에서의 요청과 응답
## 1. URLs
- 특정 경로로 요청이 왔을 때, **request 객체**를 views 모듈의 해당 함수에게 전달하며 호출

## 2. VIEW
- view 함수가 정의되는 곳
- 특정 경로에 있는 **template과 request 객체를 결합**해 응답 객체를 반환

## 3. Template
- 앱 이름을 'articles'라고 가정
- articles 앱 폴더 안에 templates 폴더 생성
- templates 폴더 안에 articles 폴더 생성
- articles 폴더 안에 템플릿 파일 생성

### template 경로 규칙
${\textsf{\color{crimson}app 폴더 / templates /}}$ articles / index.html
- Django는 빨간 지점까지 기본 경로로 인식하므로 view 함수에서 경로 작성 시 이 지점 이후의 경로를 작성해야 함