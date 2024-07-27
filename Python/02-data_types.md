# Data Types
## Numeric Types
### 1. int `정수 자료형`
- 정수를 표현하는 자료형

#### 진수 표현
- 2진수 (binary) : `0b`
- 8진수 (octal) : `0o`
- 16진수 (hexadecimal) : `0x`

---
### 2. float `실수 자료형`
- 실수를 표현하는 자료형
- 프로그래밍 언어에서 float는 실수에 대한 ${\textsf{\color{blue}근삿값}}$

#### 실수 연산 시 주의사항
- ${\textsf{\color{red}부동 소수점 에러}}$
   - 컴퓨터가 실수를 2진수로 변환하는 과정에서 발생하는 근사치 표현
- 해결책
  - 대표적으로 `decimal`모듈을 사용<br>
  ⇒ **문자열로 입력**해야함에 주의
```py
# 해결 전
a = 3.2 - 3.1
b = 1.2 - 1.1
print(a)  # 0.10000000000000009
print(b)  # 0.09999999999999987
print(a == b)  # False

# 해결 후
from decimal import Decimal

a = Decimal('3.2') - Decimal('3.1')  # 문자열로 입력
b = Decimal('1.2') - Decimal('1.1')

print(a)  # 0.1
print(b)  # 0.1
print(a == b)  # True
```

#### 지수 표현 방식
- `e` 또는 `E`를 사용한 지수 표현
```py
# 314 * 0.01
num = 314e-2

print(num)  # 3.14
print(type(num))  # <class 'float'>
```

## Sequence Types
### 1. str `문자열`
- 문자들의 순서가 있는 ${\textsf{\color{red}변경 불가능}}$한 시퀀스 자료형

#### Escape sequence
|     예약   문자    	|      내용(의미)    	|
|:------------------:	|:------------------:	|
|          `\n`        	|      줄   바꿈     	|
|          `\t`        	|          탭        	|
|          `\\`        	|       백슬래시     	|
|          `\’`        	|     작은 따옴표    	|
|          `\"`        	|     큰   따옴표    	|

#### 문자열은 불변 (변경 불가)
```py
my_str = 'hello'

# TypeError: 'str' object does not support item assignment
my_str[1] = 'z'
```

---
### 2. list `리스트`
- 여러 개의 값을 순서대로 저장하는 **변경 가능**한 시퀀스 자료형

#### 리스트는 가변 (변경 가능)
```py
my_list = [1, 2, 3]
my_list[0] = 100

print(my_list)  # [100, 2, 3]
```

---
### 3. tuple `튜플`
- 여러 개의 값을 순서대로 저장하는 ${\textsf{\color{red}변경 불가능}}$한 시퀀스 자료형

#### 튜플 표현
```py
my_tuple = (1,)
print(my_tuple)  # (1,)

# 요소가 하나일 때 ','에 유의의
my_tuple2 = (1)
print(my_tuple2)  # 1
print(type(my_tuple2))  # <class 'int'>
```

#### 튜플은 불변 (변경 불가)
```py
my_tuple = (1, 'a', 3, 'b', 5)

# TypeError: 'tuple' object does not support item assignment
my_tuple[1] = 'z'
```

#### 튜플은 어디에 쓰일까?
- 개발자가 직접 사용하기 보다는 **파이썬 내부 동작**에서 주로 사용됨
```py
x, y = (10, 20)

print(x)  # 10
print(y)  # 20

# 파이썬은 쉼표를 튜플 생성자로 사용하니 괄호는 생략 가능
x, y = 10, 20
```

---
### 4. range
- 연속된 정수 시퀀스를 생성하는 ${\textsf{\color{red}변경 불가능}}$한 자료형

## Non-sequence Types
### 1. dict `딕셔너리`
- `key - value 쌍`으로 이루어진 **순서와 중복이 없는 변경 가능**한 자료형

#### 딕셔너리 표현
- key는 **변경 불가능**한 자료형만 사용 가능 (str, int, float, tuple, range, ...)<br>
⇒ ${\textsf{\color{blue}중복이 되면 안 되므로}}$
- value는 모든 자료형 사용 가능

#### 딕셔너리 사용
- Q. 두 번째 요소를 출력하시오.
- A. print(my_dict[1])<br>
⇒ ${\textsf{\color{red}낚였습니다!!!}}$ 딕셔너리는 순서가 없으므로 **key를 통해 value에 접근**

---
### 2. set `세트`
- **순서와 중복이 없는 변경 가능한 자료형**