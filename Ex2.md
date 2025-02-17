# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## DATE:

## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```sql
UPDATE manager
SET salary = salary + (salary * 0.10),
annualsalary = annualsalary + (annualsalary * 0.10);
```

### OUTPUT:
![image](https://github.com/Sachin-vlr/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497666/5b1b1e75-0665-4a58-88b5-2cce48145f13)


### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```sql
DELETE FROM manager WHERE salary < 2750;
```

### OUTPUT:
![image](https://github.com/Sachin-vlr/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497666/00b353cb-0e93-4b33-9043-1cca563fc1dd)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```sql
SELECT ename AS "Name", salary * 12 AS "Annual Salary"
FROM manager;
```

### OUTPUT:
![image](https://github.com/Sachin-vlr/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497666/26849044-f9ea-46d6-8d0d-350026327aa4)


### Q5)	List the names of Clerks from emp table.


### QUERY:
```sql
SELECT ename from manager where designation='clerk';
```

### OUTPUT:
![image](https://github.com/Sachin-vlr/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497666/202eb760-5ce3-4335-ae81-2e9491779e63)


### Q6)	List the names of employee who are not Managers.


### QUERY:
```sql
SELECT ename from manager where designation!='manager';
```


### OUTPUT:
![image](https://github.com/Sachin-vlr/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497666/91685f67-551e-4841-8c5d-b30b64d3c2d3)


### Q7)	List the names of employees not eligible for commission.


### QUERY:
```sql
SELECT ename from manager where commission=0;
```

### OUTPUT:
![image](https://github.com/Sachin-vlr/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497666/369e0c5a-6e1f-4c90-8e9d-704e68e852e0)


### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
```sql
SELECT ename
FROM manager
WHERE ename LIKE 'S%' OR ename LIKE '%s';
```

### OUTPUT:
![image](https://github.com/Sachin-vlr/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497666/00d57877-dd70-46af-9764-f0d79e5a7391)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```sql
select ename,designation,deptno,Hiredate from manager
order by Hiredate asc;
```

### OUTPUT:
![image](https://github.com/Sachin-vlr/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497666/11cb7644-1558-499c-9879-35ed0390d4b4)


### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```sql
SELECT *
FROM manager
WHERE Hiredate < TO_DATE('1981-09-30', 'YYYY-MM-DD');
```

### OUTPUT:
![image](https://github.com/Sachin-vlr/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497666/269f269e-2c9a-4dc9-8819-48aa5691fdc6)


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```sql
select ename,deptno,salary from manager order by deptno asc;
select ename,deptno,salary from manager order by salary desc;
```

### OUTPUT:
![image](https://github.com/Sachin-vlr/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497666/b8e5c617-488b-46bc-b4db-e3c70ea089c8)


### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```sql
select ename from manager where deptno not in (10,30,40);
```

### OUTPUT:
![image](https://github.com/Sachin-vlr/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497666/187f3db6-2166-4452-82bc-a0de2156a023)


### Q13) Find number of rows in the table EMP

### QUERY:
```sql
select count(*) from manager;
```

### OUTPUT:
![image](https://github.com/Sachin-vlr/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497666/48b089c3-bed3-4437-bae6-a6df5817fa35)


### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```sql
select ename ,salary,annualsalary from manager
where salary = (select max(salary) from manager);

select ename ,salary,annualsalary from manager
where salary = (select min(salary) from manager);

select avg(salary) from manager;
```

### OUTPUT:
![image](https://github.com/Sachin-vlr/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497666/8733fd95-048a-4b30-911d-897aff659caa)


### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```sql
SELECT designation, COUNT(*) AS "Number of Employees"
FROM manager
GROUP BY designation
ORDER BY COUNT(*) DESC;
```

### OUTPUT:
![image](https://github.com/Sachin-vlr/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/113497666/c4f518cd-a36a-4f75-93d9-00ddd20d54ad)

# RESULT:
Thus, Manager database is created and DML queries such as insertion, updation, deletion are executed using SQL.

