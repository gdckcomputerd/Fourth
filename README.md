# LIST OF SQL QUERIES
![SQL]()
# FOURTH SEMESTER ASSIGNMENT ANSWERS
## Q1. Use of CREATE command to create a TABLE with PRIMARY KEY,NOT NULL,DEFAULT & FOREIGN KEY Constraint.
## Ans:
```sql
create table students(
    id int not null,
    firstname varchar(255),
    lastname varchar(255),
    age int,
    address varchar(255) default 'kishtwar',
    primary key(id)
);
//Table with foriegn key
create table subjects(
    rno int,
    stream varchar(255),
    hobby varchar(255),
    foreign key(rno) references students(id)
);
```

## Q2. Demnonstrate the use of ALTER command to ADD and DROP column of table.
## Ans:
```sql
//To add a column
alter table students
add Email varchar(255);
//To drop a column
alter table students
drop column Email;
```

## Q3. Demonstrate the use of DROP command.
## Ans:
```sql
// creating a dummy table
create table pekka(
    hp int;
    target vachar(255)
);
//using drop command
drop table pekka;
```
## Q4. Demonstrate use of RENAME command.
## Ans:
```sql
alter table students 
rename column id to rollno;
```

## Q5. Demonstrate the use of INSERT commmand.
## Ans:
```sql
insert into students
values(600,'aubrey','graham',35,'toronto');
insert into students
values(601,'Marshal','Mathers',40,'detroit');
insert into students
values(603,'loi','liang',35,'Swiss');

insert into subjects
values(600,'Bsc','singing');

insert into subjects
values(600,'BA','gaming');

```

## Q6. Demonstrate use of SELECT command.
## Ans:
```sql
select * from students;
```

## Q7. Demonstrate use of WHERE clause.
## Ans:
```sql
select lastname from students
where id=600;
```
## Q8. Demonstrate use of DELETE commmand.
## Ans:
```sql
delete from students
where id=603;
```
## Q9. Demonstrate use of UPDATE command.
## Ans:
```sql
update students
set address='LA'
where rollno=600;
```

## Q10. Demonstrate use of GROUP BY clause.
## Ans:
```sql
slect count(rollno),Age from students
group by age;
```

## Q11. Demonstrate use of HAVING clause.
## Ans:
```sql
select count(age) from students
having age >=31;
```

## Q12. Demonstrate use of LIKE clause.
## Ans:
```sql
select * from students
where lastname '%s';
```

## Q13. Demonstrate use of TOP clause.
## Ans:
```sql
select top3* fro, students;
```

## Q14. Demonstrate use of ORDER BY clause.
## Ans:
```sql
slect * from students
order by Age;
```

## Q15. Demonstrate INNER JOIN.
## Ans:
```sql
SELECT students.firstname,subjects.hobby
FROM students
INNER JOIN subjects
ON students.rollno=subjects.rno;
```

## Q16. Demonstrate LEFT OUTER JOIN.
## Ans:
```sql
select students.firstname,subjects.stream
from students
LEFT OUTER JOIN subjects
ON students.rollno=subjects.rno;
```

## Q17. Demonstrate RIGHT OUTER JOIN.
## Ans:
```sql
select subjects.rno,subjects.hobby,students.address
from students
RIGHT OUTER JOIN subjects 
ON subjects.rno = students.rollno;
```

## Q18. Demonstrate FULL OUTER JOIN.
## Ans:
```sql
select students.firstname,subjects.rno
from students
FULL OUTER JOIN subjects ON
students.rollno=subjects.rno
```

## Q19. Demonstrate the use of AVG() function in sql query.
## Ans:
```sql
select avg(age) from students
where age >= 30;
```

## Q20. Demonstrate the use of COUNT() function.
## Ans:
```sql
select count(rollno) from students
where address='LA';
```

## Q21. Demonstrate the use of MAX() function.
## Ans:
```sql
select max(age) from students;
```

## Q22. Demonstrate the use of MIN() function.
## Ans:
```sql
select min(age) from students;
```

## Q23. Demonstrate the use of SUM() function.
## Ans:
```sql
select sum(age) from students;
```

## Q24. Demonstrate the use of DATE() function.
## Ans:
```sql
SELECT ADD_MONTHS(sysdate,7) NEWDATE FROM DUAL;
SELECT ADD_MONTHS(sysdate,2) NEWDATE FROM DUAL;
SELECT CURRENT_DATE FROM Dual;
SELECT ADD_MONTHS(22-Aug-22,7) NEWDATE FROM DUAL;
SELECT sysdate FROM Dual;
```

## Q24. Demonstrate the use of CREATE VIEW STATEMENT.
```sql
CREATE VIEW students_backup AS
select rollno,firstname,age
from students
where address='LA';
```