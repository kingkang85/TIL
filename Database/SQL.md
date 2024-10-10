# Database
- 체계적인 데이터 모음


# Relational Database
- 데이터 간에 관계가 있는 데이터 항목들의 모음

## 관련 키워드
1. Table (Relation)
- 데이터를 기록하는 곳

2. Field (Column, Attribute)
- 각 필드에는 고유한 데이터 형식(타입)이 지정됨

3. Record (Row, Tuple)
- 각 레코드에는 구체적인 데이터 값이 저장됨

4. Database (Schema)
- 테이블의 집합

5. Primary Key (기본키, PK)
- 각 레코드의 고유한 값
- 관계형 데이터베이스에서 레코드의 식별자로 활용

6. Foreign Key (외래키, FK)
- 다른 테이블의 기본키를 참조
- 각 레코드에서 서로 다른 테이블 간의 관계를 만드는 데 사용

# RDBMS
- 관계형 데이터베이스를 관리하는 소프트웨어 프로그램

# SQL (Structure Query Language)
- 데이터베이스에 정보를 저장하고 처리하기 위한 프로그래밍 언어

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

## Filtering data
### DISTINCT
- 조회 결과에서 중복된 레코드를 제거
```sql
SELECT DISTINCT
  select_list
FROM
  table_name;
```

### WHERE
- 조회 시 특정 검색 조건을 지정
```sql
SELECT
  select_list
FROM
  table_name;
WHERE
  search_condition;
```

### LIMIT
- 조회하는 레코드 수를 제한
```sql
SELECT
  select_list
FROM
  table_name
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

