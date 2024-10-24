# 클래스
- 객체를 생성하기 위한 템플릿<br>
⇒ 객체의 속성, 메서드를 정의하는 청사진 역할

## 기본 문법
```javascript
class MyClass {
  // 여러 메서드를 정의할 수 있음
  constructor() { ... }
  method1() { ... }
  method2() { ... }
  method3() { ... }
  ...
}
```

## 특징
- 내부적으로 생성자 함수를 기반으로 동작
```javascript
class Member {
  // 생성자 함수
  constructor(name, age) {
    this.name = name
    this.age = age
  }
  sayHi() {
    console.log(`Hi, I am ${this.name}`)
  }
}
```

## 'new' 연산자
```javascript
const instance = new ClassName(arg1, arg2)
```
- 클래스나 생성자 함수를 사용하여 새로운 객체를 생성
- 클래스의 `constructor()`는 **new** 연산자에 의해 자동으로 호출되며 객체를 초기화 할 수 있음
- new 없이 클래스를 호출하면 TypeError 발생
