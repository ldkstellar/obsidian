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

##### unique vs primary key 차이점
| 항목             | unique | primary key |
| -------------- | ------ | ----------- |
| 중복허용           | 불가능    | 불가능         |
| Null허용         | 허용     | 불가능         |
| 한 테이블에 여러개 가능? | 가능     | 불가능         |
##### 자동 증가하는 value값


```sql
CREATE TABLE student (
student_id INT AUTO_INCREMENT, --자동 증가
name VARCHAR(20) NOT NULL,
major VARCHAR(20) UNIQUE
PRIMARY KEY(student_id)
);
```

### 비교 문법
```sql
-- equals
=
-- not equals
<>
-- greater than
>
-- greather than or equal
>=
-- less than or equal
<=

```

### find 문법
```sql
SELECT student.name, student.major from student
-- 정렬 
ORDER BY name Desc;

SELECT * FROM student

ORDER BY student_id ASC;

SELECT * FROM student

ORDER BY student_id DESC

LIMIT 3;

SELECT name ,major from student
-- 찾기
where name = 'Sam' OR name = 'Kate' ;

  

SELECT * FROM student

where student_id <=3 AND name <>'Sam'

  

SELECT * FROM student s
-- 찾기
WHERE name IN('Kante','Job')
```
