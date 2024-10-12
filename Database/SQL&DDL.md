# SQL (Structure Query Language)
- 데이터베이스에 정보를 저장하고 처리하기 위한 프로그래밍 언어

## SQL Statements 4가지 유형
1. **DDL (데이터 정의)**
  - CREATE, ALTER, DROP
2. **DQL (데이터 검색)**
  - SELECT
3. **DML (데이터 조작)**
  - INSERT, UPDATE, DELETE
4. **DCL (데이터 제어)**
  - COMMIT, ROLLBACK, GRANT, REVOKE

# DDL (데이터 정의)
## Create a table
### CREATE TABLE
- 테이블 생성
```sql
CREATE TABLE table_name (
  column_1 data_type constraints,
  column_2 data_type constraints,
  ...
);
```

### PRAGMA
- 테이블 스키마(구조) 확인
```sql
PRAGMA table_info('table_name');
```

## Modifying table fields
### ALTER TABLE
- 테이블 필드 조작
```sql
ALTER TABLE ADD COLUMN  # 필드 추가
```
```sql
ALTER TABLE RENAME COLUMN  # 필드 이름 변경
```
```sql
ALTER TABLE DROP COLUMN  # 필드 삭제
```
```sql
ALTER TABLE RENAME TO  # 테이블 이름 변경
```

## Delete a table
### DROP TABLE
- 테이블 삭제
```sql
DROP TABLE table_name;
```