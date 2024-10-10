# Web Crawling
- 웹 페이지를 자동으로 탐색하고 데이터를 수집하는 기술

## 웹 크롤링 프로세스
1. 웹 페이지 다운로드
2. 페이지 파싱
  - 다운로드 받은 코드를 분석하고 필요 데이터 추출
3. 링크 추출 및 다른 페이지 탐색
  - 다른 링크를 추출하고, 다음 단계로 이동하여 원하는 데이터 추출
4. 데이터 추출 및 저장
  - 분석 및 시각화를 위한 데이터 처리 및 저장

## 라이브러리 설치
- ${\textsf{\color{orange}requests}}$ : HTTP 요청을 보내고 응답을 받을 수 있는 모듈
- ${\textsf{\color{orange}BeautifulSoup}}$ : HTML 문서에서 원하는 데이터를 추출하는 데 사용되는 파이썬 라이브러리
- ${\textsf{\color{orange}Selenium}}$ : 웹 애플리케이션을 테스트하고 자동화하기 위한 파이썬 라이브러리

`$ pip install requests beautifulsoup4 selenium`