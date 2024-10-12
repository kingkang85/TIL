# Authentication System
## HTTP
- HTML 문서와 같은 리소스들을 가져올 수 있도록 해주는 규약
- ${\textsf{\color{crimson}비 연결 지향}}$ : 서버는 요청에 대한 응답을 보낸 후 연결을 끊음
- ${\textsf{\color{crimson}무상태}}$ : 연결을 끊는 순간 상태 정보가 유지되지 않음

## Cookie & Session
### 쿠키 (Cookie)
1. 저장 방식
  - **브라우저**는 쿠키를 KEY-VALUE 형태로 저장
  - 쿠키에는 이름, 값 외에도 만료 시간, 도메인, 경로 등의 추가 속성이 포함됨

2. 전송 과정
  - **서버**는 HTTP 응답 헤더의 Set-Cookie 필드를 통해 쿠키를 전송
  - **브라우저**는 받은 쿠키를 저장해 두었다가, 동일한 서버에 재요청시 HTTP 요청 헤더의 Cookie 필드에 저장된 쿠키를 함께 전송

3. 사용 목적
- 세션 관리 : 로그인, 아이디 자동완성, 장바구니 등의 정보 관리
- 개인화 : 사용자 선호 설정 저장
- 트래킹 : 사용자 행동을 기록 및 분석

### 세션 (Session)
- 서버 측에서 생성되어 클라이언트와 서버 간의 상태 정보를 저장<br>
⇒ 쿠키에 세션 데이터를 저장하여 요청시마다 **세션 데이터를 함께 보냄**

#### 전송 과정
- 서버 측에서는 세션 데이터를 생성 후 저장하고 ${\textsf{\color{orange}세션 ID}}$를 생성
- 이 ID를 **클라이언트 측으로 전달**하고, 클라이언트는 ${\textsf{\color{orange}쿠키에 이 ID를 저장}}$
- 클라이언트가 같은 서버에 재요청 시마다 저장해 두었던 쿠키도 요청과 함께 전송

### 쿠키와 세션의 목적
- ${\textsf{\color{crimson}클라이언트와 서버 간의 상태 정보를 유지하고 사용자를 식별하기 위해 사용}}$

## Django Authentication System
- 사용자 인증과 관련된 기능을 모아 놓은 시스템

### Custom User model
- 프로젝트의 특정 요구사항에 맞춰 사용자 모델 확장 가능

1. AbstractUser 클래스를 상속받는 커스텀 User 클래스 작성
```py
# accounts/models.py
from django.contrib.auth.models import AbstractUser

class User(AbstractUser):
  pass
```

2. AUTH_USER_MODEL 값 변경
```py
# settings.py
AUTH_USER_MODEL = 'accounts.User'  # Django 프로젝트의 User를 나타내는 모델 지정
```

3. admin site에 대체한 User 모델 등록
```py
# accounts/admin.py
from django.contrib import admin
from django.contrib.auth.admin import UserAdmin
from .models import User

admin.site.register(user, UserAdmin)
```
