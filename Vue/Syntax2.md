# Computed Properties
## computed()
- "계산된 속성"을 정의하는 함수
- 의존된 반응형 데이터를 ${\textsf{\color{orange}자동으로 추적}}$
- 의존하는 데이터가 ${\textsf{\color{orange}변경될 때만 재평가}}$

### method와의 차이
- computed 속성은 의존된 반응형 데이터가 변경되지 않는 한 이미 계산된 결과에 대한 여러 참조는 다시 평가할 필요 없이 이전에 계산된 결과를 즉시 반환
- 반면, method 호출은 다시 렌더링이 발생할 때마다 항상 함수를 실행

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

=> 콘텐츠를 매우 자주 전환해야 하는 경우에는 v-show를, 실행 중에 조건이 변경되지 않는 경우에는 v-if를 권장

# List Rendering
## v-for
소스 데이터를 기반으로 요소 또는 템플릿 블록을 여러 번 렌더링

## v-for와 v-if
- 동일 요소에 함께 사용하지 않는다!!!
- 동일 요소에서 v-if가 v-for보다 우선순위가 더 높기 때문

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
  - 1. newValue
    - 감시하는 대상이 변화된 값
  - 2. oldValue (optional)
    - 감시하는 대상의 기존 값