# Form
## 개요
### HTML 'Form'
- 사용자로부터 데이터를 제출 받기 위해 활용한 방법
- 그러나 비정상적 혹은 악의적인 요청을 필터링 할 수 없음<br>

⇒ ${\textsf{\color{orange}유효한 데이터인지}}$에 대한 확인이 필요

## Form Class
### Django 'Form'
- 사용자 입력 데이터를 수집하고, 처리 및 유효성 검사를 수행하기 위한 도구<br>
⇒ 유효성 검사를 단순화하고 자동화 할 수 있는 기능을 제공

### Form class 정의
```py
from django import forms

class ArticleForm(forms.Form):
  title = forms.CharField(max_length=10)
  content = forms.CharField()
```

### Widgets
- HTML 'input' element의 표현을 담당
- 단순히 input 요소의 속성 및 출력되는 부분을 변경하는 것

```py
class ArticleForm(forms.Form):
  content = forms.CharField(widget=forms.TextArea)
```

## Django ModelForm
### Form vs Django ModelForm
- Form : 사용자 입력 데이터를 DB에 저장하지 않을 때 (ex. 검색, 로그인)
- ModelForm : 사용자 입력 데이터를 ${\textsf{\color{crimson}DB에 저장}}$해야 할 때 (ex. 게시글 작성, 회원가입)

### ModelForm
- Model과 연결된 Form을 자동으로 생성해주는 기능을 제공<br>
⇒ ${\textsf{\color{crimson}Form + Model}}$

### ModelFrom class 정의
```py
from django import forms
from .models import Article

class ArticleForm(forms.ModelForm):
  class Meta:
    model = Article
    fields = '__all__'
```