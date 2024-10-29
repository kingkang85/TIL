# 비동기
특정 작업의 실행이 완료될 때가지 기다리지 않고 다음 작업을 즉시 실행하는 방식 <br>
⇒ 작업의 완료 여부를 신경 쓰지 않고 ${\textsf{\color{crimson}동시에 다른 작업들을 수행할 수 있음}}$

## 특징
- 병렬적 수행
- 시간이 필요한 작업들은 백그라운드에서 실행되며 빨리 완료되는 작업부터 처리

## JavaScript와 비동기
### Single Thread 언어, JavaScript
Thread란? <br>
작업을 처리할 때 실제로 작업을 수행하는 주체로, multi-thread라면 업무를 수행할 수 있는 주체가 여러 개라는 의미

- JavaScript는 하나의 작업을 요청한 순서대로 처리
- 그럼 어떻게 비동기 처리?

### JavaScript Runtime
- JavaScript의 비동기 처리를 도와주는 환경

**브라우저 환경에서의 JavaScript 비동기 처리 동작 방식**
1. Call Stack
모든 작업은 Call Stack(LIFO)으로 들어간 후 처리

2. Web API
오래 걸리는 작업이 Call Stack으로 들어오면 Web API로 보내 별도로 처리

3. Task Queue
Web API에서 처리가 끝난 작업들은 Task Queue(FIFO)에 순서대로 들어감

4. Event Loop
Call Stack이 비어 있는 것을 계속 체크하고 Task Queue에서 가장 먼저 처리되어 들어온 작업을 Call Stack으로 보냄

## Ajax (Asynchronous JavaScript and XML)
- 비동기적인 웹 애플리케이션 개발을 위한 기술
- Ajax를 사용하면 페이지 전체를 새로고침 하지 않고도 동적으로 데이터를 불러와 화면을 갱신할 수 있음

### XMLHttpRequest 객체
- JavaScript를 사용하여 서버에 HTTP 요청을 할 수 있는 객체
- 웹 페이지의 전체 새로고침 없이도 서버로부터 데이터를 가져오거나 보낼 수 있음

## Axios
브라우저와 Node.js에서 사용할 수 있는 Promise 기반의 HTTP 클라이언트 라이브러리
- 브라우저를 위한 XHR 객체 생성

### 서버 간 동작
XHR 객체 생성 및 요청 -> 응답 데이터 생성 -> JSON 데이터 응답 -> Promis 객체 데이터를 활용해 DOM 조작

### 기본 구조
- 성공 처리
  - then 메서드 사용
  - 서버로부터 받은 응답 데이터를 처리

- 실패 처리
  - catch 메서드 사용
  - 네트워크 오류나 서버 오류 등의 예외 상황을 처리

## Callback과 Promise
