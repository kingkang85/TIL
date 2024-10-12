# DQL (데이터 검색)
## Querying data
### SELECT
- 테이블에서 데이터를 조회
```sql
SELECT select_list FROM table_name;
```
- `SELECT` 키워드 이후 필드 하나 이상 지정
- `FROM` 이후 데이터를 선택하려는 테이블의 이름을 지정

## Sorting data
### ORDER BY
- 조회 결과의 레코드를 정렬
- 하나 이상의 컬럼을 기준으로 결과를 오름차순(ASC, 기본 값), 내림차순(DESC)으로 정렬
- NULL 값이 존재할 경우 오름차순 정렬 시 결과에 NULL이 먼저 출력

## Filtering data
### DISTINCT
- 조회 결과에서 중복된 레코드를 제거
```sql
SELECT DISTINCT select_list FROM table_name;
```

### WHERE
- 조회 시 특정 검색 조건을 지정
```sql
SELECT select_list FROM table_name
WHERE search_condition;
```

### LIMIT
- 조회하는 레코드 수를 제한
```sql
SELECT select_list FROM table_name
LIMIT [offset, ] row_count;
```
- `row_count`는 조회하는 최대 레코드 수를 지정

## Grouping data
### GROUP BY
- 레코드를 그룹화하여 요약본 생성
- 집계 함수와 함께 사용

**Aggregation Fuctions (집계 함수)**
- 값에 대한 계산을 수행하고 단일한 값을 반환하는 함수
- SUM, AVG, MAX, MIN, COUNT

### HAVING
- 집계 항목에 대한 세부 조건을 지정
- 주로 GROUP BY와 함께 사용되며 GROUP BY가 없다면 WHERE처럼 동작