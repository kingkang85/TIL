# Classes
## 1. 객체 지향 프로그래밍
### 절차 지향과 객체 지향
> #### 절차 지향
- 데이터와 해당 데이터를 처리하는 함수(절차)가 분리
- 함수 호출의 흐름이 중요

> #### 객체 지향
- 데이터와 해당 데이터를 처리하는 메서드를 하나의 객체(클래스)로 묶음
- 객체 간 상호작용과 메시지 전달이 중요

## 2. 클래스
- 파이썬에서 타입을 표현하는 방법
- **객체를 생성하기 위한 설계도**
- 붕어빵 틀이라고 생각

### 클래스 구성요소
1. 생성자 함수
- 객체(인스턴스)를 생성할 때 자동으로 호출되는 특별한 메서드
- `__init__`이라는 이름의 메서드로 정의되며, **객체의 초기화**를 담당

2. 인스턴스 변수
- 인스턴스(객체)마다 별도로 유지되는 변수
- 인스턴스마다 독립적인 값을 가지며, 인스턴스가 생성될 때마다 초기화됨

3. 클래스 변수
- 클래스 내부에 선언된 변수
- 클래스로 생성된 **모든 인스턴스들이 공유**하는 변수

4. 인스턴스 메서드
- 각각의 인스턴스에서 호출할 수 있는 메서드

## 3. 객체
- <span style='color:orange;'>속성</span>과 <span style='color:orange;'>행동</span>으로 구성된 모든 것
  - 속성 == 변수
  - 행동 == 메서드
- 틀로 찍어낸 붕어빵이라고 생각

## 4. 인스턴스
- 클래스로 만든 객체를 인스턴스라고 부름
- ex) 가수(클래스)<br>
    → 아이유는 객체다 (O)<br>
    → 아이유는 인스턴스다 (X)<br>
    → 아이유는 가수의 인스턴스다 (O)

> 즉, 하나의 객체(object)는 특정 타입의 인스턴스(instance)

## 5. 메서드
### 메서드 종류
1. 인스턴스 메서드
- 반드시 첫 번째 매개변수로 <span style='color:orange;'>인스턴스 자신(`self`)</span>을 전달받음
```py
class MyClass:
  
  def instance_method(self, arg1, ...):
    pass
```
- self의 동작 원리
  - 'hello'.upper()
  - 파이썬 실제 내부 동작 : str.upper('hello')
  - str 클래스가 upper 메서드를 호출했고, 그 첫 번째 인자로 문자열 인스턴스가 들어간 것
  - <span style='color:red;'>인스턴스 메서드의 첫 번째 매개변수가 반드시 인스턴스 자기 자신인 이유</span>

2. 생성자 메서드
- 위의 클래스 구성요소 참조
```py
class Person:
  def __init__(self, name):
    self.name = name
```

3. 클래스 메서드
- 클래스가 호출하는 메서드
- `@classmethod` 데코레이터를 사용하여 정의
- 호출 시, 첫 번째 인자로 호출하는 클래스(cls)가 전달됨
```py
class MyClass:

  @classmethod
  def class_method(cls, arg, ...):
    pass
```

4. 정적 메서드
- 클래스와 인스턴스와 상관 없이 독립적으로 동작하는 메서드<br> 
⇒ 단지 기능만을 위한 메서드로 사용
- `@staticmethod` 데코레이터를 사용하여 정의
- 호출 시 필수적으로 작성해야 할 매개변수가 없음

### 누가 어떤 메서드를 사용해야 할까?!
- 클래스가 사용해야 할 것
  - <span style='color:orange;'>클래스 메서드</span>
  - <span style='color:orange;'>스태틱 메서드</span>

- 인스턴스가 사용해야 할 것
  - <span style='color:orange;'>인스턴스 메서드</span>

# 상속
- 기존 클래스의 속성과 메서드를 물려받아 새로운 하위 클래스를 생성

## 다중 상속
- 둘 이상의 상위 클래스로부터 여러 행동이나 특징을 상속받음
- **중복**된 속성이나 메서드가 있는 경우 <span style='color:red;'>상속 순서에 의해 결정</span>

## `super()`
- 부모 클래스 객체를 반환하는 내장 함수
### 사용 예시
#### super() 사용 예시 (다중 상속)
```py
class ParentA:
    def __init__(self):
        self.value_a = 'ParentA'

    def show_value(self):
        print(f'Value from ParentA: {self.value_a}')


class ParentB:
    def __init__(self):
        self.value_b = 'ParentB'

    def show_value(self):
        print(f'Value from ParentB: {self.value_b}’)


class Child(ParentA, ParentB):
    def __init__(self):
        super().__init__() # ParentA 클래스의 __init__ 메서드 호출
        self.value_c = 'Child’

    def show_value(self):
        super().show_value() # ParentA 클래스의 show_value 메서드 호출
                             # ParentB의 것을 쓰고 싶을 때는 ParentB.show_value()
        print(f'Value from Child: {self.value_c}')

child = Child()
child.show_value()
```