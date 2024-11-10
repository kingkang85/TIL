# Computed Properties
## computed()
- "계산된 속성"을 정의하는 함수
- 의존된 반응형 데이터를 ${\textsf{\color{orange}자동으로 추적}}$
- 의존하는 데이터가 ${\textsf{\color{orange}변경될 때만 재평가}}$

### method와의 차이
- **computed 속성**은 의존된 반응형 데이터가 변경되지 않는 한 이미 계산된 결과에 대한 여러 참조는 재평가 없이 이전에 계산된 결과를 즉시 반환
- 반면, **method 호출**은 다시 렌더링이 발생할 때마다 항상 함수를 실행

## computed와 method의 적절한 사용처
- computed
  - 의존하는 데이터에 따라 결과가 바뀌는 계산된 속성을 만들 때 유용
  - 동일한 의존성을 가진 여러 곳에서 사용할 때 중복 계산 방지
- method
  - 단순히 특정 동작을 수행하는 함수를 정의할 때 사용
  - 항상 동일한 결과를 반환하는 함수

# Conditional Rendering
## v-if
표현식 값의 true/false를 기반으로 요소를 조건부로 렌더링

## v-show
표현식 값의 true/false를 기반으로 요소의 가시성을 전환

## v-if vs v-show
### 적절한 사용처
- v-if
  - 초기 조건이 false인 경우 아무 작업도 수행하지 않음
  - 토글 비용이 높음

- v-show
  - 초기 조건에 관계 없이 항상 렌더링
  - 초기 렌더링 비용이 더 높음

⇒ 콘텐츠를 매우 자주 전환해야 하는 경우에는 **v-show**를, 실행 중에 조건이 변경되지 않는 경우에는 **v-if**를 권장

# List Rendering
## v-for
소스 데이터를 기반으로 요소 또는 템플릿 블록을 여러 번 렌더링

## v-for와 v-if
- ${\textsf{\color{crimson}동일 요소에 함께 사용하지 않는다!!!}}$
- 동일 요소에서 **v-if**가 v-for보다 **우선순위가 더 높기** 때문

### 해결법
1. ${\textsf{\color{orange}computed를 활용해 이미 필터링된 목록을 반환하여 반복}}$하도록 설정
2. v-for와 **template** 요소를 사용하여 ${\textsf{\color{orange}v-if 위치를 이동}}$

# Watchers
## watch()
하나 이상의 반응형 데이터를 감시하고, 감시하는 데이터가 변경되면 콜백 함수를 호출
```js
watch(source, (newValue, oldValue) => {
  // do something
})
```
- 첫 번째 인자 (source)
  - watch가 감시하는 대상
- 두 번째 인자 (callback function)
  - source가 변경될 때 호출되는 콜백 함수
  1. newValue : 감시하는 대상이 변화된 값
  2. oldValue (optional) : 감시하는 대상의 기존 값

## computed vs watchers
### 공통점
- 데이터의 변화를 감지하고 처리
- 의존(감시)하는 원본 데이터를 직접 변경하지 않음

### 동작
- computed : 의존하는 데이터 속성의 계산된 값을 반환
- watchers : 특정 데이터 속성의 변화를 감시하고 작업을 수행

### 사용 목적
- computed : 계산한 값을 캐싱하여 재사용 / 중복 계산 방지
- watchers : 데이터 변화에 따른 특정 작업을 수행