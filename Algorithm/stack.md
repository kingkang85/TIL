# 24.08.06.
# 스택 (Stack)
- 자료를 쌓아 올린 형태의 자료구조
- 선형 구조
- ${\textsf{\color{red}LIFO (후입선출)}}$ : 마지막에 삽입한 자료를 가장 먼저 꺼냄

## 스택의 연산
- **삽입 (push)** : 자료 저장
- **삭제 (pop)** : 자료 꺼냄
- isEmpty : 스택이 공백인지 아닌지 확인
- peek : 스택의 top에 있는 item 반환 (개수가 줄지 않으므로 pop과는 다름)

## 스택의 구현
- push 알고리즘
```py
def push(item):
  s.append(item)
```

- pop 알고리즘
```py
def pop():
  if len(s) == 0:  # underflow
    return
  else:
    return s.pop()
```

underflow, overflow 항상 잘 고려하자 ~!!

### 스택의 응용 : Fuction call
- 가장 마지막에 호출된 함수가 가장 먼저 실행을 완료하고 복귀하는 LIFO 구조이므로, **스택을 이용하여 수행 순서 관리**
- `함수 호출이 발생하면` 지역변수, 매개변수 및 수행 후 복귀할 주소 등을 스택 프레임에 저장하여 시스템 스택에 삽입
- `함수의 실행이 끝나면` 시스템 스택의 top 원소를 삭제(pop)하면서 프레임에 저장된 복귀 주소를 확인하고 복귀

## 재귀호출
- 자신을 다시 호출하는 구조
