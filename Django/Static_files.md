# Static files
- 서버 측에서 변경되지 않고 고정적으로 제공되는 파일
  - (이미지, JS, CSS 파일 등)

## Static files 기본 경로
- **app폴더/static/**
- DTL의 'static tag'를 사용
  - built-in tag가 아니므로 `{% load static %}`으로 import 후 사용 가능

### STATIC_URL
- 기본 경로 및 추가 경로에 위치한 정적 파일을 참조하기 위한 URL
  - 실제 파일이나 디렉토리 경로가 아니며, URL로만 존재

```py
# settings.py
STATIC_URL = 'static/'
```

⇒ URL + ${\textsf{\color{crimson}STATIC\_URL}}$ + ${\textsf{\color{orange}정적 파일 경로}}$

## Static files 추가 경로
- STATICFILES_DIRS에 문자열 값으로 추가 경로 설정<br>

```py
# settings.py
STATICFILES_DIRS = [
  BASE DIR / 'static',
]
```

⇒ **정적 파일을 제공하려면 요청에 응답하기 위한 URL이 필요**

# Media files
- 사용자가 웹에서 업로드하는 정적 파일 (user-uploaded)

## 준비사항
- settings.py에 MEDIA_ROOT, MEDIA_URL 설정
```py
# settings.py
MEDIA_ROOT = BASE_DIR / 'media'  # 미디어 파일들이 위치하는 디렉토리의 절대 경로
MEDIA_URL = 'media/'  # 미디어 파일에 대한 주소 생성
```

- 작성한 MEDIA_ROOT와 MEDIA_URL에 대한 URL 지정
```py
# 프로젝트의 urls.py
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [
  ...
] + static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT)
```

## 이미지 업로드
1. **모델에 ImageField() 추가**
  - 이미지 업로드에 사용하는 모델 필드
  - ${\textsf{\color{crimson}이미지 파일의 경로}}$ 문자열이 저장됨
  - pillow 라이브러리 필요 → `pip install pillow`

2. **migration 진행**

3. **form 요소의 enctype 속성 추가**<br>
`enctype="multipart/form-data`

4. **ModelForm의 2번째 인자로 요청 받은 파일 데이터 작성**<br>
`form = ArticleForm(request.POST, request.FILES)`

## 업로드 이미지 제공하기
- article.image.url
  - 업로드 파일의 경로

- article.image
  - 업로드 파일의 파일 이름