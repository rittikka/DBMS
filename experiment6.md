# EXPERIMENT6

##  1: Display empno, ename, deptno from employee table. Instead of displaying department numbers display the related department name (Use CASE function).
```sql
SELECT empno,
       ename,
       CASE deptno
            WHEN 10 THEN 'ACCOUNTING'
            WHEN 20 THEN 'RESEARCH'
            WHEN 30 THEN 'SALES'
            WHEN 40 THEN 'OPERATIONS'
            ELSE 'UNKNOWN'
       END AS department_name
FROM employee;
```
## 2 :  Display your age in days.
```sql
SELECT DATEDIFF(CURDATE(), '2006-07-04') AS age_in_days;
```
## 3: Display your age in months.
```sql
SELECT TIMESTAMPDIFF(MONTH, '2006-07-04', CURDATE()) AS age_in_months;
```
## 4. Display the current date as 15th August Friday 1990 format.
```sql
SELECT DATE_FORMAT(CURDATE(), '%D %M %W %Y') AS formatted_date;
```
## 5,6. Scott has joined the company on Wednesday 13th August 1990. Display the following output for each row from employee table:
```sql
SELECT CONCAT(ename,
              ' has joined the company on ',
              DATE_FORMAT(hiredate, '%W %D %M %Y')) AS joining_info
FROM employee;
```
## 7. Find the date for nearest Saturday after current date
```sql
SELECT DATE_ADD(CURDATE(), INTERVAL (5 - WEEKDAY(CURDATE())) DAY) AS NEXT_SATURDAY;
```
## 8. Display current time.
```sql
SELECT CURTIME() AS current_time;
```
## 9. Display the date three months before the current date.
```sql
SELECT DATE_SUB(CURDATE(), INTERVAL 3 MONTH) AS three_months_before;
```
## 10. Display those employees who joined in the month of December.
```sql
SELECT *
FROM employee
WHERE MONTH(hiredate) = 12;
```
## 11. Display those employees whose first 2 characters from hire date = last 2 characters of salary.
```sql
SELECT * FROM EMPLOYEE 
WHERE RIGHT(DATE_FORMAT(HIREDATE,'%Y'),2) = RIGHT(SAL,2);
```
## 12. Display those employees whose 10% of salary is equal to the year of joining.
```sql
SELECT *
FROM employee
WHERE sal * 0.10 = YEAR(hiredate);
```
## 13. Display those employees who joined the company before 15th of the month.
```sql
SELECT *
FROM employee
WHERE DAY(hiredate) < 15;
```
## 14. Display those employees who joined after 15th of the month
```sql
SELECT *
FROM employee
WHERE DAY(hiredate) > 15;
```
## 15. Display those employees whose joining DATE is available in deptno.
```sql
SELECT *
FROM employee
WHERE deptno IS NOT NULL;
```

