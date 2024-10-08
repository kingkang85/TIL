# Django Model
- DB의 테이블을 정의하고 데이터를 조작할 수 있는 기능들을 제공<br>
⇒ 테이블 구조를 설계하는 청사진

## Model 클래스 작성
Ariticle이라는 모델 클래스 작성
```py
from django.db import models

class Article(models.Model):
    title = models.CharField(max_length=10)
    content = models.TextField()
```
- django.db.models 모듈의 Model이라는 부모 클래스를 상속받음
- **클래스 변수명** (ex. title, content) : 테이블의 각 ${\textsf{\color{blue}필드 이름}}$
- **Model Field** : 데이터의 유형과 제약 조건을 정의

### Model Field
- DB 테이블의 ${\textsf{\color{crimson}필드}}$를 정의하며, 해당 필드에 저장되는 ${\textsf{\color{crimson}데이터 타입}}$과 ${\textsf{\color{crimson}제약 조건}}$을 정의

- Field Types
    - 데이터베이스에 저장될 **데이터의 종류**를 정의
    - ex) CharField(), TextField() ...

- Field Options
    - 필드의 **동작**과 **제약 조건**을 정의
    - ex) max_length, null, blank, default ...

## Migrations
- model 클래스의 변경사항(필드 생성, 수정, 삭제 등)을 DB에 최종 반영하는 방법

### Migrations 과정
1. model class (설계도 초안)<br>
↓ ${\textsf{\color{crimson}makemigrations}}$
2. migration 파일 (최종 설계도)<br>
↓ ${\textsf{\color{crimson}migrate}}$
3. db.sqlite3 (DB)

### 핵심 명령어 2가지
- `python manage.py makemigrations`
    - model class를 기반으로 최종 설계도 작성

- `python manage.py migrate`
    - 최종 설계도를 DB에 전달하여 반영