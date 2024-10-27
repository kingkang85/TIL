# Object (객체)
키로 구분된 데이터 집합을 저장하는 자료형

## 객체 구조
- 중괄호('{}')를 이용해 작성
- 중괄호 안에는 **key: value** 쌍으로 구성된 속성을 여러 개 작성 가능
- key는 문자형만 허용
- value는 모든 자료형 허용

## Method (메서드)
객체 속성에 정의된 함수<br>
⇒ ${\textsf{\color{orange}this}}$ 키워드를 사용해 객체에 대한 특정한 작업을 수행할 수 있음

### this
- 함수나 메서드를 호출한 객체를 가리키는 키워드<br>
⇒ 함수 내에서 객체의 속성 및 메서드에 접근하기 위해 사용

- JavaScript의 함수는 호출될 때 this를 암묵적으로 전달 받음
- JavaScript에서 this는 함수가 "호출되는 방식"에 따라 결정되는 현재 객체를 나타냄
- ${\textsf{\color{crimson}함수가 호출되기 전까지 값이 할당되지 않고 호출 시에 결정}}$됨 (동적 할당)

## 객체 문법
### 계산된 속성
  - 키가 대괄호([])로 둘러싸여 있는 속성<br>
  ⇒ 고정된 값이 아닌 변수 값을 사용할 수 있음
  ```javascript
  const product = prompt('물건 이름을 입력해주세요')
  const prefix = 'my'
  const suffix = 'property'

  const bag = {
    [product]: 5,
    [prefix + suffix]: 'value',
  }
  console.log(bag) // {연필: 5, myproperty: 'value'}
  ```

### 구조 분해 할당
  - 배열 또는 객체를 분해하여 객체 속성을 변수에 쉽게 할당할 수 있는 문법
  ```javascript
  const userInfo = {
    firstName: 'Alice',
    userId: 'alice123',
    email: 'alice123@gmail.com'
  }
  const { firstName, userId, email } = userInfo
  console.log(firstName, userId, email) // Alice alice123 alice123@gmail.com
  ```

  - '함수의 매개변수'로 객체 구조 분해 할당 활용 가능
  ```javascript
  const person = {
    name: 'Bob',
    age: 35,
    city: 'London',
  }

  function printInfo({ name, age, city }) {
    console.log(`이름: ${name}, 나이: ${age}, 도시: ${city}`)
  }

  // 함수 호출 시 객체를 구조 분해하여 함수의 매개변수로 전달
  printInfo(person) // 이름: Bob, 나이: 35, 도시: London
  ```

### Object with '전개 구문'
  - 객체 내부에서 객체 전개
  - 얕은 복사에 활용 가능
  ```javascript
  const obj = {b: 2, c: 3, d: 4}
  const newObj = {a: 1, ...obj, e: 5}
  console.log(newObj) // {a: 1, b: 2, c: 3, d: 4, e: 5}
  ```

### Optional chaining (?.)
  - 참조가 누락될 가능성이 있는 경우 연결된 속성으로 접근할 때 사용
  - 존재하지 않아도 괜찮은 대상에만 사용 (남용 X)
  - Optional chaining 앞의 변수는 반드시 선언되어 있어야 함

## JSON
- Key-Value 형태로 이루어진 자료 표기법
- JavaScript의 Object와 유사한 구조를 가지고 있지만 JSON은 형식이 있는 ${\textsf{\color{crimson}문자열}}$
- Object <-> JSON 변환
```javascript
// Object -> JSON
const objToJson = JSON.stringify(jsObject)

// JSON -> Object
const jsonToObj = JSON.parse(objToJson)
```