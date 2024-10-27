# Function (함수)
참조 자료형에 속하며 모든 함수는 Function object

## 함수 정의 2가지 방법
### 선언식
```javascript
function funcName() {
  statements
}
```
- 호이스팅 됨
- 코드의 구조와 가독성 면에서는 표현식에 비해 장점이 있음

### 표현식
```javascript
const funcName = function () {
  statements
}
```
- 호이스팅 되지 않음
  - 변수 선언만 호이스팅되고 함수 할당은 실행 시점에서 이루어짐
- 함수 이름이 없는 '익명 함수'를 사용할 수 있음

## 매개변수
### 기본 함수 매개변수
전달하는 인자가 없거나 undefined가 전달될 경우 이름 붙은 매개변수를 기본값으로 초기화

### 나머지 매개변수
- 임의의 수의 인자를 '배열'로 허용하여 가변 인자를 나타내는 방법
- 함수 정의 시 나머지 매개변수는 하나만 작성 가능
- 나머지 매개변수는 마지막에 위치

### 매개변수와 인지 개수가 불일치 할 때
- 누락된 인자는 undefined로 할당
- 초과 입력한 인자는 사용하지 않음

## Function with '전개 구문'
- 함수 호출 시 인자 확장
- 나머지 매개변수 (압축)

## 화살표 함수 표현식
함수 표현식의 간결한 표현법
```javascript
const arrow = function (name) {
  return `Hello, ${name}`
}
```
```javascript
const arrow = (name) => { return `Hello, ${name}` }
```