# DBMS Practical 1– Employee Master Table

## Step 1: Create department table
```sql
CREATE TABLE department(
    -> deptno int(2) PRIMARY KEY,
    -> dname VARCHAR(15) NOT NULL);
```
---
## Step 2 : Create employee table
```sql
CREATE TABLE employee(
    -> empno int(4) PRIMARY KEY,
    -> ename varchar(20) NOT NULL,
    -> job varchar(20) ,
    -> mgr int(4),
    -> hiredate DATE,
    -> sal int(10),
    -> comm int(7),
    -> deptno int(2),
    -> FOREIGN KEY (deptno) REFERENCES department (deptno)
    -> ); 
```
---
## Step 3 : Insert values into department
```sql
INSERT INTO department VALUES
    -> (10 , 'research'),
    -> (20 , 'accounting'),
    -> (30 , ' sales '),
    -> (40 , 'operations');
```
---
## Step 4 : Insert values into employee
```sql
INSERT INTO employee VALUES
    -> (7369,'SMITH','CLERK',7902,'1980-12-17',800,NULL,20),
    -> (7499,'ALLEN','SALESMAN',7698,'1981-02-20',1600,300,30),
    -> (7521,'WARD','SALESMAN',7698,'1981-02-22',1250,300,30),
    -> (7566,'JONES','MANAGER',7839,'1981-04-02',2975,NULL,20),
    -> (7654,'MARTIN','SALESMAN',7698,'1981-09-28',1250,1400,30),
    -> (7698,'BLAKE','MANAGER',7839,'1981-05-01',2850,NULL,30),
    -> (7782,'CLARK','MANAGER',7839,'1981-06-09',2450,NULL,20),
    -> (7788,'SCOTT','ANALYST',7566,'1982-12-09',3000,NULL,40),
    -> (7839,'KING','PRESIDENT',NULL,'1981-11-17',5000,NULL,20),
    -> (7844,'TURNER','SALESMAN',7698,'1981-09-08',1500,NULL,30),
    -> (7876,'ADAMS','CLERK',7788,'1983-01-12',1100,NULL,20),
    -> (7900,'JAMES','CLERK',7698,'1981-12-03',950,NULL,30),
    -> (7902,'FORD','ANALYST',7566,'1981-12-03',3000,NULL,20),
    -> (7934,'MILLER','CLERK',7782,'1982-01-23',1300,NULL,10);
```
---
## Step 5: Create Employee_master table using Employee table
Query:
```sql
CREATE TABLE employee_master AS
SELECT * FROM employee;
```
---
## Step 6: Delete all records where DeptNo = 10
```sql
 DELETE FROM employee_master
    -> WHERE deptno = 10;
```
---
## Step 7: Increase salary by 10% for DeptNo = 20
```sql
UPDATE employee_master
    -> SET sal= sal+(sal*0.10)
    -> WHERE deptno = 20
```
---
## Step 8: Alter SAL column size to (10,2)    
```sql
ALTER TABLE employee_master
    -> MODIFY sal DECIMAL(10,2);
Query OK, 13 rows affected (0.096 sec)
```
---
## Step 9: Drop Employee_master table
```sql
DROP TABLE employee_master;anga
```
---