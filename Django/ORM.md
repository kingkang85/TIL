# ORM (Object Relational Mapping)
- 객체 지향 프로그래핑 언어를 사용하여 호환되지 않는 유형의 시스템 간에 ${\textsf{\color{blue}데이터를 변환}}$하는 기술

## QuerySet API
- ORM에서 데이터를 검색, 필터링, 정렬 및 그룹화 하는 데 사용되는 도구

### Query
- 데이터베이스에 특정한 데이터를 보여 달라는 요청
- 파이썬으로 작성한 코드가 ORM에 의해 SQL로 변환되어 데이터베이스에 전달됨
- 데이터베이스의 응답 데이터를 ORM이 QuerySet이라는 자료 형태로 변환하여 전달

### QuerySet
- 데이터베이스에게서 전달 받은 객체 목록 (데이터 모음)
- Django ORM을 통해 만들어진 자료형
- 단, **단일 객체는 모델(Class)의 인스턴스로 반환**됨
<br>

⇒ 즉, QuerySet API는 python의 모델 클래스와 인스턴스를 활용해 ${\textsf{\color{orange}DB에 데이터를 저장, 조회, 수정, 삭제하는 것}}$

## CRUD
### Create (저장)
**방법 1**
```ipython
>>> article = Article()  # Article(class)로부터 article(instance) 생성

>>> article.title = 'first'  # 인스턴수 변수(title)에 값 할당
>>> article.content = 'django!'  # 인스턴스 변수(content)에 값 할당

>>> article.save()  # save를 하지 않으면 DB에 값이 저장되지 않음
```

**방법 2**
```ipython
>>> article = Article(title='second', content='django!')
>>> article.save()
```

**방법 3**
```ipython
>>> Article.objects.create(title='third', contect='django!')
```

### Read (조회)
- Return new QuerySets
```ipython
>>> Article.objects.all()  # 전체 데이터 조회

>>> Ariticle.objects.filter(content='django!')  # 주어진 매개변수와 일치하는 객체를 포함하는 QuerySet 반환
```

- Do not return QuerySets
```ipython
>>> Article.objects.get(pk=1)  # 주어진 매개변수와 일치하는 객체를 반환

>>> Article.objects.get(pk=100)  # DoesNotExist 에러 : 없는 객체 요청 시

>>> Article.objects.get(content="django!")  # MultipleObjectsReturned 에러 : 둘 이상의 객체를 찾을 시
```
- ${\textsf{\color{crimson}primary key와 같이 고유성을 보장하는 조회에서 사용}}$

### Update (갱신)
```ipython
>>> article = Article.objects.get(pk=1)  # 수정할 인스턴스 조회부터 !!
>>> article.title = "byebye"
>>> article.save()
```

### Delete (삭제)
```ipython
>>> article = Article.objects.get(pk=1)  # 삭제할 인스턴스 조회부터 !!
>>> article.delete()
```