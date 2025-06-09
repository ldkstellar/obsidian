```sql
INT --전체숫자
DECIMAL(10,4) --소수
BLOB --binary large object,stores large data
DATE --'YYYY-MM-DD'
TIMESTAMP -- 'YYYY-MM-DD HH:MM:SS'
```

##### 테이블 만들기

```sql
CREATE TABLE student (
student_id INT PRIMARY KEY,
name VARCHAR(20) NOT NULL,
major VARCHAR(20) UNIQUE
);
```

##### 테이블 보기
describe table_name;

##### 테이블 삭제
drop table table_name;
