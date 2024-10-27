# Variable (변수)
## 변수명 작성 규칙
- 반드시 문자, 달러('$') 또는 밑줄('_')로 시작
- 대소문자를 구분
- 예약어 사용 불가

## 변수 선언 키워드
### let
- 블록 스코프를 갖는 지역 변수를 선언
- 재할당 가능
- 재선언 불가능
```javascript
let number = 10  // 1. 선언 및 초기값 할당
number = 20  // 2. 재할당

let number2 = 10  // 1. 선언 및 초기값 할당
let number2 = 20  // 2. 재선언 불가능
```

### const
- 블록 스코프를 갖는 지역 변수를 선언
- 재할당 불가능
- 재선언 불가능
- ${\textsf{\color{crimson}선언 시 반드시 초기값 설정 필요}}$

**블록 스코프 (block scope)**
- if, for, 함수 등의 ${\textsf{\color{orange}중괄호 내부}}$를 가리킴
- 블록 바깥에서 접근 불가능
```javascript
let x = 1

if (x === 1) {
  let x = 2
  console.log(x)  // 2
}

console.log(x)  // 1
```