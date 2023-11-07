# EX 3 SubQueries, Views and Joins 
## Date: 18/08/23
## AIM: 
To create a manager database and execute DML queries using SQL.
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

![270762717-1848b392-372d-4111-af2d-25daf5458864](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/e0c5e121-2f21-400c-bdbd-742bc72395a8)

### OUTPUT:

![270762784-ee7dd795-bf87-4dff-aca9-b80307477ddd](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/d39c1f65-15cf-4135-b98d-7a09420e65a8)

### Q2) List the ename,job,sal of the employee who get minimum salary in the company.

### QUERY:

![270763155-2c78d720-f077-4843-bbbd-cefb0e36afcf](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/20e57d2d-be41-4e9b-a0ff-391322185a5f)

### OUTPUT:

![270763212-0ca9e7dc-c9b6-45c6-b7a0-bf123d815295](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/da6966ea-7913-4607-a0de-bbf2218f63ed)

### Q3) List ename, job of the employees who work in deptno 10 and his/her job is any one of the job in the department ‘SALES’.

### QUERY:

![270764132-ea1201a0-53bc-436b-b815-3889759afcff](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/8040d921-3ec1-4b4d-b07d-354dc6ac442b)

### OUTPUT:

![270764187-7376ae95-bab6-4739-abd7-bdc5e8a727dd](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/eb4207d6-e80f-4a1d-a2b3-2c68dd2cf567)

### Q4) Create a view empv5 (for the table emp) that contains empno, ename, job of the employees who work in dept 10.

### QUERY:

![270764614-4c3e781f-8787-461d-b2ee-162f5222abd9](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/b3079e4f-76af-4a24-9763-d1343b18c59a)

### OUTPUT:

![270764656-753d1db9-8955-4b97-b850-43622886968b](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/d535ff3c-2aef-4a29-9dbd-8395d922f290)

### Q5) Create a view with column aliases empv30 that contains empno, ename, sal of the employees who work in dept 30. Also display the contents of the view.

### QUERY:

![270765070-3551ed65-3cb5-4846-b817-48436b507530](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/1bf0b0de-1319-4412-90f2-cbb02d9a487c)

### OUTPUT:

![270765159-026712b5-02b2-40d6-a757-cec5bc08890d](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/21982e49-ac55-4941-8429-449933a7946c)


### Q6) Update the view empv5 by increasing 10% salary of the employees who work as ‘CLERK’. Also confirm the modifications in emp table

### QUERY:

![270767939-d83bbdcd-83a3-427e-bd2b-e799958b055d](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/2d5e4834-3d3e-4a1d-844d-c6a89c876a4f)

### OUTPUT:

![270767871-6941b531-33ed-41dc-b6f4-9e8bcc0dd113](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/bf1071f6-d4d2-4e96-bdf5-a06de3b81637)

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

![270771248-20c63405-1555-444c-8d92-daee8ad9f52d](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/eb4c1493-35db-458f-9cae-f69832406402)

### OUTPUT:

![270771306-4bf9b80e-b31d-486e-87b5-5462e60e6e2f](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/ddc3c4ba-11e6-4672-aa5e-1da6adb27873)

### Q8) Write a SQL query to find salespeople who received commissions of more than 13 percent from the company. Return Customer Name, customer city, Salesman, commission.

### QUERY:

![270772008-6b4b7f1a-e1fa-41eb-abfc-d544b005a00e](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/6df12dbf-a3ae-4310-a765-9b00577e028a)

### OUTPUT:

![270772054-031553d8-640c-4306-9f12-cd4a6c6a68ed](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/8b213a97-dc47-46f1-a5ea-7cea08a0a992)

### Q9) Perform Natural join on both tables

### QUERY:

![270772360-a9609769-7404-4c74-909b-53d5610ea79a](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/aebde1dd-d42d-4ea8-a539-ec67932e6f02)

### OUTPUT:

![270772421-1026e100-8a70-45e8-bdcb-3d51efdfa1fc](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/19f96e17-6297-42c1-a39f-6cc1862fa87e)

### Q10) Perform Left and right join on both tables

### QUERY:
### Left Join:

![270849330-7915ee92-d1e0-4528-be68-4bbe6fd7a11c](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/3a8a4353-c210-4757-94da-1c8ba13a3117)

### Right Join:

![image](https://github.com/DhanushPalani/EX-3-SubQueries-Views-and-Joins/assets/121594640/8be146f2-c02a-4c31-8dd7-a759a92e69c3)

### OUTPUT:

### Left Join:

![270773161-f7e2b17f-33d1-404c-8a43-83636dc8c552](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/eaa2199e-49fe-4e8c-855f-6c4ff801fae5)

### Right Join:

![270773439-43cc7093-35af-4c4b-8854-068a0f0b34d1](https://github.com/22008539/EX-3-SubQueries-Views-and-Joins/assets/118707617/5379867e-4fbe-4adb-8453-f1e494f75988)
## RESULT:
Hence successfully created a manager database and execute DML queries using SQL.
