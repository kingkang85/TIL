# Component
재사용 가능한 코드 블록

## 특징
- UI를 독립적이고 재사용 가능한 일부분으로 분할하고 각 부분을 개별적으로 다룰 수 있음

## Single-File Components (SFC)
- 컴포넌트의 템플릿, 로직 및 스타일을 하나의 파일로 묶어낸 특수한 파일 형식
- Vue SFC는 HTML, CSS 및 JavaScript를 단일 파일로 합친 것

## SFC 구성 요소
- 각 *.vue 파일은 세 가지 유형의 최상위 언어 블록 <template>, <script>, <style>으로 구성됨
- 각 *.vue 파일은 최상위 <template> 블록을 하나만 포함할 수 있음
- <script setup> 블록을 하나만 포함할 수 있음 (일반 <script> 제외)
- 컴포넌트의 setup() 함수로 사용되며 컴포넌트의 각 인스턴스에 대해 실행
- 여러 <style> 태그 포함될 수 있음
- scoped가 지정되면 CSS는 현재 컴포넌트에만 적용됨

# SFC build tool
## Vite
프론트 엔드 개발 도구 <br>
⇒ 빠른 개발 환경을 위한 빌드 도구와 개발 서버를 제공

### Build
- 프로젝트의 소스 코드를 최적화하고 번들링하여 배포할 수 있는 형식으로 변환하는 과정
- 개발 중에 사용되는 여러 소스 파일 및 리소스(JavaScript, CSS, 이미지 등)를 최적화된 형태로 조합하여 최종 소프트웨어 제품을 생성하는 것<br>
⇒ Vite는 이러한 빌드 프로세스를 수행하는 데 사용되는 도구

### Vue Project
- `npm create vue@latest` : Vue Project (Application) 생성
- `cd vue-project` : 프로젝트 폴더 이동
- `npm install` : 패키지 설치
- `npm run dev` : Vue 프로젝트 서버 실행

### Node Package Manager (NPM)
Node.js의 기본 패키지 관리자

## 모듈과 번들러
### Module
프로그램을 구성하는 독립적인 코드 블록 (*.js 파일)
- 개발하는 애플리케이션의 크기가 커지고 복잡해지면서 파일 하나에 모든 기능을 담기가 어려워짐
- 따라서 자연스럽게 파일을 여러 개로 분리하여 관리를 하게 되었고, 이때 분리된 각 파일이 바로 모듈<br>
⇒ *.js 파일 하나가 하나의 모듈
- 하지만 점점 더 발전함에 따라 처리해야 하는 JavaScript 모듈의 개수도 극적으로 증가

### Bundler
여러 모듈과 파일 하나(혹은 여러 개)의 번들로 묶어 최적화하여 애플리케이션에서 사용할 수 있게 만들어주는 도구

## 컴포넌트 사용 2단계
1. 컴포넌트 파일 생성
2. 컴포넌트 등록 (import)