# Vue Router
## Routing
네트워크에서 경로를 선택하는 프로세스

⇒ 웹 애플리케이션에서 다른 페이지 간의 전환과 경로를 관리하는 기술

## Basic Routing
1. index.js에 라우터 관련 설정 작성 (주소, 이름, 컴포넌트)
```js
// index.js
const router = createRouter({
  routes: [
    {
      path: '/',
      name: 'home',
      component: HomeView
    },
    ...
  ]
})
```

2. RouterLink의 'to' 속성으로 index.js에서 정의한 주소값(path)을 사용
```vue
<!-- App.vue -->
<RouterLink to="/">Home</RouterLink>
<RouterLink to="/about">About</RouterLink>
```

3. RouterLink 클릭 시 경로와 일치하는 컴포넌트가 RouterView에서 렌더링 됨
```vue
<!-- App.vue -->
<RouterView />
```

## Dynamic Route Matching
URL의 일부를 변수로 사용하여 경로를 동적으로 매칭

## Nested Routing

## Programmatic Navigation
RouterLink 대신 JavaScript를 사용해 페이지를 이동하는 것

### router의 메서드
1. 다른 위치로 이동하기
- `router.push()`


2. 현재 위치 바꾸기
- `router.replace()`

