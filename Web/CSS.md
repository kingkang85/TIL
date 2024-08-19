# CSS (Cascading Style Sheet)
## 적용 방법
1. 인라인 스타일
- HTML 요소 안에 style 속성 값으로 작성
2. 내부 스타일 시트
- head 태그 안에 style 태그에 작성
3. 외부 스타일 시트
- 별도 CSS 파일 생성 후 HTML link 태그를 사용해 불러오기

# CSS Selectors
- HTML 요소를 선택하여 스타일을 적용할 수 있도록 하는 선택자


# 명시도
- 결과적으로 요소에 적용할 CSS 선언을 결정하기 위한 알고리즘

## 높은 순
1. !important
2. Inline 스타일
3. 선택자 : id 선택자 > class 선택자 > 요소 선택자
4. 소스 코드 선언 순서

거의 class 선택자를 씀 why? 우선순위 생각하지 않고 스타일을 입히기 위해 ...
id는 왜 안 씀? 요소 1개에만 적용함 ... 중복이 안 되는구나..

# 상속
왤케 빨라 진자;;

# css box model
- 박스는 좌측 상단에서 시작
1. outer display type
  - block : 아래로 떨어짐  h1 h2 p 보면 밑으로 떨어짐 (너비 영역 다 차지)
  - inline : 옆으로 감  a img 태그 보면 옆으로 감  (본인의 컨텐츠 영역 차지)
