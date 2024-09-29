# Admin Site
## Automatic admin interface
- Django가 추가 설치 및 설정 없이 자동으로 제공하는 관리자 인터페이스<br>
⇒ 데이터 확인 및 테스트 등을 진행하는데 매우 유용

1. **admin 계정 생성**<br>
`python manage.py createsuperuser`

2. **DB에 생성된 admin 계정 확인**

3. **admin에 모델 클래스 등록**
- admin.py에 작성한 모델 클래스 등록
- 이 과정을 거쳐야만 admin site에서 확인 가능

4. **admin site 로그인 후 등록된 모델 클래스 확인**

5. **데이터 생성, 수정, 삭제 테스트**

6. **테이블 확인**