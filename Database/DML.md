# DML (데이터 조작)
## Insert data
### INSERT
- 테이블 레코드 삽입
```sql
INSERT INTO table_name (c1, c2, ...)
VALUES (v1, v2, ...);
```
- `INSERT INTO` 절 다음에 테이블 이름과 괄호 안에 필드 목록 작성
- `VALUES` 키워드 다음 괄호 안에 해당 필드에 삽입할 값 목록 작성

## Update data
### UPDATE
- 테이블 레코드 수정
```sql
UPDATE table_name
SET column_name = expression, ...
[WHERE condition];
```
- `SET` 절 다음에 수정할 필드와 새 값을 지정
- `WHERE` 절에서 수정할 레코드를 지정하는 조건 작성
  - 작성하지 않으면 모든 레코드를 수정

## Delete data
### DELETE
- 테이블 레코드 삭제
```sql
DELETE FROM table_name
[WHERE condition];
```