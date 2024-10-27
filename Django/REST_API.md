# REST API
- API Server를 개발하기 위한 일종의 소프트웨어 설계 방법론
- ${\textsf{\color{crimson}자원을 정의}}$하고 ${\textsf{\color{crimson}자원에 대한 주소를 지정}}$하는 전반적인 방법
1. 자원의 "식별"
  - URI
2. 자원의 "행위"
  - HTTP Methods
3. 자원의 "표현"
  - JSON 데이터 (궁극적으로 표현되는 데이터 결과물)

## 자원의 식별
### URI
- 인터넷에서 리소스를 식별하는 문자열
- 가장 일반적인 URI는 웹 주소로 알려진 **URL**

### URL
- 웹에서 주어진 리소스의 주소
- 네트워크 상에 리소스가 어디 있는지 알려주기 위한 약속

## 자원의 행위
### GET
- 서버에 리소스의 표현을 요청
- GET을 사용하는 요청은 데이터만 검색해야 함

### POST
- 데이터를 지정된 리소스에 제출
- 서버의 상태를 변경

### PUT
- 요청한 주소의 리소스를 수정

### DELETE
- 지정된 리소스를 삭제

## 자원의 표현
- JSON 데이터

# DRF with Single Model
## Serialization (직렬화)
- 여러 시스템에서 활용하기 위해 데이터 구조나 객체 상태를 나중에 재구성할 수 있는 포맷으로 변환하는 과정

## Serializer
- Serialization을 진행하여 Serialized data를 반환해주는 클래스

## ModelSerializer
- Django 모델과 연결된 Serializer 클래스
- 사용자 입력 데이터를 받아 자동으로 모델 필드에 맞추어 Serialization을 진행