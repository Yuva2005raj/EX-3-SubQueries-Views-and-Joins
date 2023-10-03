# EX 3 SubQueries, Views and Joins 

# AIM:
To create a database and execute DDL queries like views and joins using SQL.


## Create employee Table
```sql
CREATE TABLE EMP (EMPNO NUMBER(4) PRIMARY KEY,ENAME VARCHAR2(10),JOB VARCHAR2(9),MGR NUMBER(4),HIREDATE DATE,SAL NUMBER(7,2),COMM NUMBER(7,2),DEPTNO NUMBER(2));
```
## Insert the values
```sql
INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7369, 'SMITH', 'CLERK', 7902, '17-DEC-80', 800, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7499, 'ALLEN', 'SALESMAN', 7698, '20-FEB-81', 1600, 300, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7521, 'WARD', 'SALESMAN', 7698, '22-FEB-81', 1250, 500, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7566, 'JONES', 'MANAGER', 7839, '02-APR-81', 2975, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7654, 'MARTIN', 'SALESMAN', 7698, '28-SEP-81', 1250, 1400, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7698, 'BLAKE', 'MANAGER', 7839, '01-MAY-81', 2850, NULL, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7782, 'CLARK', 'MANAGER', 7839, '09-JUN-81', 2450, NULL, 10);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7788, 'SCOTT', 'ANALYST', 7566, '19-APR-87', 3000, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7839, 'KING', 'PRESIDENT', NULL, '17-NOV-81', 5000, NULL, 10);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7844, 'TURNER', 'SALESMAN', 7698, '08-SEP-81', 1500, 0, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7876, 'ADAMS', 'CLERK', 7788, '23-MAY-87', 1100, NULL, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7900, 'JAMES', 'CLERK', 7698, '03-DEC-81', 950, NULL, 30);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7902, 'FORD', 'ANALYST', 7566, TO_DATE('03-DEC-81', 'DD-MON-RR'), 3000, 20, 20);

INSERT INTO EMP (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO)
VALUES (7934, 'MILLER', 'CLERK', 7782, TO_DATE('23-JAN-82', 'DD-MON-RR'), 1300, 10, 10);
```

## Create department table
```sql
CREATE TABLE DEPT (DEPTNO NUMBER(2) PRIMARY KEY,DNAME VARCHAR2(14),LOC VARCHAR2(13));
```
## Insert the values in the department table
```sql
INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (10, 'ACCOUNTING', 'NEW YORK');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (20, 'RESEARCH', 'DALLAS');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (30, 'SALES', 'CHICAGO');

INSERT INTO DEPT (DEPTNO, DNAME, LOC) VALUES (40, 'OPERATIONS', 'BOSTON');
```

### Q1) List the name of the employees whose salary is greater than that of employee with empno 7566.


### QUERY:
```
SQL> SELECT ename FROM emp1 WHERE sal > (SELECT sal FROM emp1 WHERE empno = 7566);
```


### OUTPUT:
![exp3_DBMS-1](https://github.com/Yuva2005raj/EX-3-SubQueries-Views-and-Joins/assets/118343998/d0f7db74-6bc2-4a22-8ad5-16bc9e195e0c)


### Q2) List the ename,job,sal of the employee who get minimum salary in the company.

### QUERY:
```
SQL> SELECT ename, job, sal FROM emp1 WHERE sal = (SELECT min(sal) FROM emp1);
```


### OUTPUT:
![exp3_DBMS-2](https://github.com/Yuva2005raj/EX-3-SubQueries-Views-and-Joins/assets/118343998/ed351ca3-5f99-49c9-8226-1ceb48ba0d1c)


### Q3) List ename, job of the employees who work in deptno 10 and his/her job is any one of the job in the department ‘SALES’.

### QUERY:
```
SQL> SELECT ename, job FROM emp1 WHERE deptno = 10 AND job IN (SELECT job FROM emp1 WHERE job = 'SALES');
```


### OUTPUT:
![exp3_DBMS-3](https://github.com/Yuva2005raj/EX-3-SubQueries-Views-and-Joins/assets/118343998/8a59b4b5-3c38-493d-9d8b-9f7fa5660806)



### Q4) Create a view empv5 (for the table emp) that contains empno, ename, job of the employees who work in dept 10.

### QUERY:
```
SQL> CREATE VIEW empv5 AS SELECT empno, ename, job FROM emp1 WHERE deptno = 10;
```


### OUTPUT:
![exp3_DBMS-4](https://github.com/Yuva2005raj/EX-3-SubQueries-Views-and-Joins/assets/118343998/b7647e61-8f53-4815-997d-d5ea10275acf)


### Q5) Create a view with column aliases empv30 that contains empno, ename, sal of the employees who work in dept 30. Also display the contents of the view.

### QUERY:
```
SQL> CREATE VIEW empv30 AS SELECT empno AS "EMPLOYEE NUMBER", ename AS "EMPLOYEE NAME", sal AS "SALARY" FROM emp1 WHERE deptno = 30;
```



### OUTPUT:
![exp3_DBMS-5](https://github.com/Yuva2005raj/EX-3-SubQueries-Views-and-Joins/assets/118343998/f9bbb753-f1d4-46a4-9e6c-7248b68c20fd)

### Q6) Update the view empv5 by increasing 10% salary of the employees who work as ‘CLERK’. Also confirm the modifications in emp table

### QUERY:
```
SQL> UPDATE empv5 SET sal = sal * 1.1 WHERE job = 'CLERK';
```


### OUTPUT:
![exp3_DBMS-6](https://github.com/Yuva2005raj/EX-3-SubQueries-Views-and-Joins/assets/118343998/791da582-532f-479a-8d19-8b33e0f89fdf)


## Create a Customer1 Table
```sql
CREATE TABLE Customer1 (customer_id INT,cust_name VARCHAR(20),city VARCHAR(20),grade INT,salesman_id INT);
```
## Inserting Values to the Table
```sql
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3002, 'Nick Rimando', 'New York', 100, 5001);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3007, 'Brad Davis', 'New York', 200, 5001);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3005, 'Graham Zusi', 'California', 200, 5002);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3008, 'Julian Green', 'London', 300, 5002);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3004, 'Fabian Johnson', 'Paris', 300, 5006);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3009, 'Geoff Cameron', 'Berlin', 100, 5003);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3003, 'Jozy Altidor', 'Moscow', 200, 5007);
INSERT INTO Customer1 (customer_id, cust_name, city, grade, salesman_id) VALUES(3001, 'Brad Guzan', 'London', NULL, 5005);
```
## Create a Salesperson1 table
```sql
CREATE TABLE Salesman1 (salesman_id INT,name VARCHAR(20),city VARCHAR(20),commission DECIMAL(4,2));
```
## Inserting Values to the Table
```sql
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5001, 'James Hoog', 'New York', 0.15);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5002, 'Nail Knite', 'Paris', 0.13);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5005, 'Pit Alex', 'London', 0.11);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5006, 'Mc Lyon', 'Paris', 0.14);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5007, 'Paul Adam', 'Rome', 0.13);
INSERT INTO Salesman1 (salesman_id, name, city, commission) VALUES(5003, 'Lauson Hen', 'San Jose', 0.12);
```
### Q7) Write a SQL query to find the salesperson and customer who reside in the same city. Return Salesman, cust_name and city.

### QUERY:
```
SQL> SELECT salesman1.name AS "Salesman", customer1.cust_name AS "Customer Name", salesman1.city AS "City" FROM salesman1 INNER JOIN customer1 ON salesman1.city = customer1.city;
```

### OUTPUT:
![exp3_DBMS-7](https://github.com/Yuva2005raj/EX-3-SubQueries-Views-and-Joins/assets/118343998/fd5d6858-ee23-44a2-86ef-e0459b0a491f)


### Q8) Write a SQL query to find salespeople who received commissions of more than 13 percent from the company. Return Customer Name, customer city, Salesman, commission.


### QUERY:
```
SQL> SELECT customer1.cust_name AS "Customer Name", customer1.city AS "Customer City", salesman1.commission AS "Commission" FROM salesman1 INNER JOIN customer1 ON salesman1.salesman_id = customer1.salesman_id WHERE salesman1.commission > 0.13;
```


### OUTPUT:
![exp3_DBMS-8](https://github.com/Yuva2005raj/EX-3-SubQueries-Views-and-Joins/assets/118343998/04d45e5c-1db2-4009-a9ff-2e056db19c7a)


### Q9) Perform Natural join on both tables

### QUERY:
```
SQL> SELECT * FROM customer1 NATURAL JOIN salesman1;
```

### OUTPUT:
![exp3_DBMS-9](https://github.com/Yuva2005raj/EX-3-SubQueries-Views-and-Joins/assets/118343998/4133eb26-fc44-4903-9629-6ce7863c07a6)


### Q10) Perform Left and right join on both tables

### QUERY:
```
SQL> SELECT * FROM salesman1 LEFT JOIN customer1 ON salesman1.salesman_id = customer1.salesman_id;
SQL> SELECT * FROM salesman1 RIGHT JOIN customer1 ON salesman1.salesman_id = customer1.salesman_id;
```


### OUTPUT:
![exp3_DBMS-10(1)](https://github.com/Yuva2005raj/EX-3-SubQueries-Views-and-Joins/assets/118343998/b0ae5fee-adb6-41d2-938e-1244e2956504)


![exp3_DBMS-10(2)](https://github.com/Yuva2005raj/EX-3-SubQueries-Views-and-Joins/assets/118343998/464eec89-10b8-4ffe-af85-c12146966ff3)


## RESULT:
Thus, DDL queries like views and joins using SQL has been implemented successfully.
