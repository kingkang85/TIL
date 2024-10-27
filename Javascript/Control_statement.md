# 조건문
## if 예시
```javascript
const name = 'customer'

if (name === 'admin') {
  console.log('관리자님 환영해요!')
} else if (name === 'customer') {
  console.log('고객님 환영해요!')
} else {
  console.log(`반갑습니다. ${name}님!`)
}
```

## 삼항 연산자 
`condition ? expression1 : expression2`
- condition : 평가할 조건
- expression1 : 조건이 **true**일 경우 반환할 값 또는 표현식
- expression2 : 조건이 **false**일 경우 반환할 값 또는 표현식

# 반복문
## 반복문 종류
### while
조건문이 참이면 문장을 계속해서 수행
```javascript
while (조건문) {
  // do something
}
```

### for
특정 조건이 거짓으로 판별될 때까지 반복
```javascript
for ([초기문]; [조건문]; [증감문]) {
  // do something
}
```

### for ... in
객체의 열거 가능한 속성(property)에 대해 반복
```javascript
for (variable in object) {
  statement
}
```

### for ... of
반복 가능한 (순서가 있는) 객체에 대해 반복
```javascript
for (variable of iterable) {
  statement
}
```