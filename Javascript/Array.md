# Array
- 순서가 있는 데이터 집합을 저장하는 자료구조

## 배열 구조
- 대괄호('[]')를 이용해 작성
- 요소의 자료형은 제약 없음
- length 속성을 사용해 배열에 담긴 요소 개수 확인 가능

## 배열 메서드
- push / pop : 배열 끝 요소를 추가 / 제거
- unshift / shift : 배열 앞 요소를 추가 / 제거

## Array Helper Methods
- 배열 조작을 보다 쉽게 수행할 수 있는 특별한 메서드 모음
- 배열의 각 요소를 ${\textsf{\color{crimson}순회}}$하며 각 요소에 대해 함수(${\textsf{\color{crimson}콜백함수}}$)를 호출

### 콜백 함수 (Callback function)
- 다른 함수에 인자로 전달되는 함수<br>
⇒ 외부 함수 내에서 호출되어 일종의 루틴이나 특정 작업을 진행

### forEach
- 배열의 각 요소를 반복하며 모든 요소에 대해 함수(콜백 함수)를 호출
- 반환 값 없음<br>
`arr.forEach(callback(item[, index[, array]]))`
  - item : 처리할 배열의 요소
  - index : 처리할 배열 요소의 인덱스
  - array : forEach를 호출한 배열

### map
- 배열의 모든 요소에 대해 함수(콜백함수)를 호출하고, 반한 된 호출 결과 값을 모아 ${\textsf{\color{orange}새로운 배열을 반환}}$<br>
`arr.map(callback(item,[, index[, array]]))`