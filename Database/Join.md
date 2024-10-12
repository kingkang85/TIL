# Join
- 둘 이상의 테이블에서 데이터를 검색하는 방법

## INNER JOIN
- 두 테이블에서 값이 일치하는 레코드에 대해서만 결과를 반환
```sql
SELECT select_list FROM table_a
INNER JOIN table_b
  ON table_b.fk = table_a.pk;
```
- `INNER JOIN` 절 이후 메인 테이블과 조인할 테이블을 지정
- `ON` 키워드 이후 조인 조건을 작성

## LEFT JOIN
- 오른쪽 테이블과 일치하는 레코드와 함께 왼쪽 테이블의 모든 레코드 반환
```sql
SELECT select_list FROM table_a
LEFT JOIN table_b
  ON table_b.fk = table_a.pk;
```