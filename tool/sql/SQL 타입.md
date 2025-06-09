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
student_id INT PRIMARY KEY, --단독키
name VARCHAR(20) NOT NULL,
major VARCHAR(20) UNIQUE -- 
);
```

##### 테이블 보기
describe table_name;

##### 테이블 삭제
drop table table_name;

##### 테이블 추가 변경

```sql
ALTER TABLE student ADD gpa DECIMAL(3,2)  -- ADD
ALTER TABLE student DROP COLUMN gpa; --remove
```

##### row 추가하기
```sql
INSERT INTO student VALUES(1,'Kate','Sociology');
INSERT INTO student(student_id,name,major) VALUES(4,'Claire','gym');
```

##### row 수정하기
```sql
UPDATE student SET name ="LEE" where student_id =4;
```
