# EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands
## AIM:
To create a manager database and execute DML queries using SQL.


### DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

### List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

```
 Program Developed by: Chethan kumar G
 Register number: 212222240022
```

### Create the table as given below:
```sql
create table MANAGER(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
### Insert the following values into the table:
```sql
insert into MANAGER values(7369,'Chethan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into MANAGER values(7839,'Dileep',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into MANAGER values(7934,'Samer',3500,300,42000,'1-May-82','manager',30,NULL);
insert into MANAGER values(7788,'Dharnesh',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```
#### OUTPUT:
![Screenshot 2023-10-16 142707](https://github.com/Gchethankumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118348224/96527452-f570-468c-9400-9fcbdf2caae2)

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.
#### QUERY:
```sql
 UPDATE MANAGER SET SALARY = SALARY + (SALARY * 10/100);
```
#### OUTPUT:
![Screenshot 2023-10-16 142726](https://github.com/Gchethankumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118348224/ef010bb3-f86d-416e-a0dd-312d535d9289)


### Q2) Delete the records from manager table where the salary less than 2750.
#### QUERY:
```sql
delete from MANAGER where salary < 2750;
```
#### OUTPUT:
![Screenshot 2023-10-16 142745](https://github.com/Gchethankumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118348224/9418cca5-669f-499a-a9cc-e93439b1f719)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary).
#### QUERY:
```sql
select ename as "Name",salary * 12 as "Annual Salary" from MANAGER;
```
#### OUTPUT:
![Screenshot 2023-10-16 142757](https://github.com/Gchethankumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118348224/9b540323-b01c-4724-96d5-3ae86d6e155b)


### Q5)	List the names of Clerks from emp table.
#### QUERY:
```sql
select ename from MANAGER where designation = 'clerk';
```
#### OUTPUT:
![Screenshot 2023-10-16 142808](https://github.com/Gchethankumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118348224/cce43251-f4f7-495e-9869-f9c6894f262f)


### Q6)	List the names of employee who are not Managers.
#### QUERY:
```sql
select ename from MANAGER where designation <> 'manager';
```
#### OUTPUT:
![Screenshot 2023-10-16 142818](https://github.com/Gchethankumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118348224/13860e12-fd4e-4e13-ba46-c10a151f55c9)


### Q7)	List the names of employees not eligible for commission.
#### QUERY:
```sql
select ename from MANAGER where commission = 0;
```
#### OUTPUT:
![Screenshot 2023-10-16 142842](https://github.com/Gchethankumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118348224/943999cf-1ef5-43f2-9e66-598584eade65)


### Q8)	List employees whose name either start or end with ‘s’.
#### QUERY:
```sql
select ename from MANAGER where ename like '%s' or ename like 's%';
```
#### OUTPUT:
![Screenshot 2023-10-16 142854](https://github.com/Gchethankumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118348224/6591e54c-e119-434f-b5b5-e0f371c28d04)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.
#### QUERY:
```sql
select ename,designation as "job",deptno,hiredate from MANAGER order by hiredate asc;
```
#### OUTPUT:
![Screenshot 2023-10-16 142907](https://github.com/Gchethankumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118348224/163bdd2b-bd16-4754-aa04-9e543ab5a3e8)


### Q10) List the Details of Employees who have joined before 30 Sept 81.
#### QUERY:
```sql
select * from MANAGER where hiredate<to_date('1981-09-30','YYYY-MM-DD')
```
#### OUTPUT:
![Screenshot 2023-10-16 142917](https://github.com/Gchethankumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118348224/7d57fbef-c4f2-46f9-8812-d7f06c46500b)

### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.
#### QUERY:
```sql
select ename,deptno,salary from MANAGER order by deptno asc,salary desc;
```
#### OUTPUT:
![Screenshot 2023-10-16 142929](https://github.com/Gchethankumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118348224/33c360cc-3f4d-49ae-93cc-304de4ff21e4)


### Q12) List the names of employees not belonging to dept no 30,40 & 10.
#### QUERY:
```sql
select ename from MANAGER where deptno not in (30,40,10);
```
#### OUTPUT:
![Screenshot 2023-10-16 142938](https://github.com/Gchethankumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118348224/ed8b4185-1c78-4c65-bbcc-026d7564ecaa)


### Q13) Find number of rows in the table EMP.
#### QUERY:
```sql
select count(*) from MANAGER;
```
#### OUTPUT:
![Screenshot 2023-10-16 142946](https://github.com/Gchethankumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118348224/0c4cbc9a-7ecd-4125-84dd-690f31356f23)


### Q14) Find maximum, minimum and average salary in EMP table.
#### QUERY:
```sql
select max(salary) from MANAGER;
select min(salary) from MANAGER;
select avg(salary) from MANAGER;
```
#### OUTPUT:
![Screenshot 2023-10-16 142956](https://github.com/Gchethankumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118348224/0fd7a8fa-4ade-4294-a090-09f46370af71)


### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

#### QUERY:
```sql
SELECT designation AS job, count(*) AS num_employees from MANAGER GROUP BY designation ORDER BY num_employees DESC;
```
#### OUTPUT:
![Screenshot 2023-10-16 143012](https://github.com/Gchethankumar/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/118348224/597412f1-c3c9-466b-a96b-1accf4e83fff)

## RESULT:
To create a manager database and execute DML queries using SQL is executed successfully.
