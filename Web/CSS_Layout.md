# CSS Layout
- 각 요소의 위치와 크기를 조정하여 웹 페이지의 디자인을 결정하는 것
  - Display, Position, Flexbox

## CSS Position
- 요소를 Normal Flow에서 제거하여 다른 위치로 배치
- ex ) 다른 요소 위에 올리기, 화면의 특정 위치에 고정시키키 등

- static
- absolute: 가장 가까운 relative 기준으로 옮겨
- relative: 밑에 fixed가 차고 올라가지 않아 왜? 원래 본인 static 영역을 버리지 않아
- fixed : viewport 기준으로 이동
- sticky : 특정 임계점에 도달하기 전에는 relative처럼 도달하면 fixed처럼 동작

## CSS Flexbox
- Inner display type
- 요소를 행과 열 형태로 배치하는 1차원 레이아웃 방식
- Flex Container (부모)
- Flex Item (자식)
- 부모 안의 요소를 옮긴다고 생각. 각각의 요소를 옮기는 것이 아님 !!