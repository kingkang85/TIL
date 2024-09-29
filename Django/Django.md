# Django
## 개요
### Web Framework
- 웹 애플리케이션을 빠르게 개발할 수 있도록 도와주는 도구
  - (개발에 필요한 기본 구조, 규칙, 라이브러리 등을 제공)

## Django Web Framework
- Python 기반의 대표적인 웹 프레임워크

### 가상환경 세팅
- Python 애플리케이션과 그에 따른 패키지들을 격리하여 관리할 수 있는 ${\textsf{\color{crimson}독립적인}}$ 실행 환경

1. **가상 환경 venv 생성**<br>
`python -m venv venv`

2. **가상 환경 활성화**<br>
`source venv/Scripts/activate`

3. **환경에 설치된 패키지 목록 확인**<br>
`pip list`

4. **설치된 패키지 목록 생성**<br>
`pip freeze > requirements.txt`
  - 현재 Python 환경에 설치된 모든 패키지와 그 버전을 텍스트 파일로 저장
  - requirements.txt : 생성될 파일 이름 (관례적으로 사용)
  - 패키지 목록 기반 설치
    - `pip install -r requirements.txt`

### Django 프로젝트
- 애플리케이션의 집합 (DB 설정, URL 연결, 전체 앱 설정 등을 처리)

1. **프로젝트 생성**<br>
`django-admin startproject 프로젝트명 .`

2. **서버 실행**<br>
`python manage.py runserver`

### Django 애플리케이션
- 독립적으로 작동하는 기능 단위 모듈

1. **앱 생성**<br>
`python manage.py startapp 앱이름`

2. ${\textsf{\color{orange}앱 등록}}$<br>
앱을 생성한 후 settings.py의 INSTALLED_APPS에 반드시 등록!!

## Django Design Pattern
### 디자인 패턴
  - 소프트웨어 설계에서 발생하는 문제를 해결하기 위한 일반적인 해결책

### MVC 디자인 패턴 (Model, View, Controller)
  - 애플리케이션을 데이터, 사용자 인터페이스, 비즈니스 로직으로 분리한 대표적인 패턴

### MTV 디자인 패턴 (Model, Template, View)
  - Django에서 단순히 MVC 패턴의 명칭을 다르게 정의한 것