# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
<img width="857" height="511" alt="image" src="https://github.com/user-attachments/assets/ef1f302d-ee90-410f-905e-5774d971bea9" />


```sql
select * from customer where grade>100;
```

**Output:**
<img width="863" height="436" alt="image" src="https://github.com/user-attachments/assets/6457a3dc-e05a-461a-bb15-55a4424afb7e" />


**Question 2**
---
<img width="795" height="359" alt="image" src="https://github.com/user-attachments/assets/0f505ab8-4cf9-415f-85fe-253a66131586" />


```sql
update products set category = "Household" where product_name like '%Detergent%';
```

**Output:**

<img width="863" height="579" alt="image" src="https://github.com/user-attachments/assets/81545f75-1e2c-44d2-a4c0-fc8180418b61" />


**Question 3**
---
<img width="869" height="362" alt="image" src="https://github.com/user-attachments/assets/e7e5840e-3942-4f44-a38c-fc1715c94201" />


```sql
delete from customer where cust_city LIKE 'L%';
```

**Output:**

<img width="841" height="657" alt="image" src="https://github.com/user-attachments/assets/8fb493fe-dac7-4dad-a02f-ec312b82a6a8" />


**Question 4**
---
<img width="852" height="376" alt="image" src="https://github.com/user-attachments/assets/03f50d26-f590-466b-9fa9-3967c5967fa1" />


```sql
SELECT product_id,original_price,discount_percentage,(original_price*discount_percentage) as discount_amount FROM Products where original_price*discount_percentage>50;
```

**Output:**

<img width="889" height="304" alt="image" src="https://github.com/user-attachments/assets/cfdc01d0-9516-4074-a80f-422193a1e58e" />


**Question 5**
--
-<img width="870" height="478" alt="image" src="https://github.com/user-attachments/assets/a22dfaba-14d1-4a36-8cbb-7234efadf8db" />

```sql
delete from Doctors where doctor_id between 2 and 4;
```

**Output:**

<img width="811" height="555" alt="image" src="https://github.com/user-attachments/assets/1d4b59d5-f3d4-4cb2-b3a9-6f956b00c6fb" />


**Question 6**
---
<img width="856" height="528" alt="image" src="https://github.com/user-attachments/assets/3afdfe5a-ec3e-43f4-b520-0aa61cbc694d" />


```sql
select SUBSTR(Address,1,INSTR(Address,'(')-1) as PlaceName from EmployeeInfo;
```

**Output:**

<img width="728" height="337" alt="image" src="https://github.com/user-attachments/assets/39dd13d8-39ff-4d1c-bd50-68b7a79f5f7b" />


**Question 7**
---
<img width="842" height="362" alt="image" src="https://github.com/user-attachments/assets/d980cbdd-dda2-4f86-aca3-0589df37aed9" />


```sql
delete from Customer where (GRADE>2 AND PAYMENT_AMT<(SELECT AVG(PAYMENT_AMT)FROM Customer))
OR OUTSTANDING_AMT>8000;
```

**Output:**

<img width="765" height="528" alt="image" src="https://github.com/user-attachments/assets/83a345f0-874d-4256-842f-14865b4ba639" />


**Question 8**
---
<img width="825" height="457" alt="image" src="https://github.com/user-attachments/assets/9ca934ed-7b92-4741-bf7c-11b5673027c7" />


```sql
select COUNT(*) from EmployeeInfo where Department='HR';
```

**Output:**

<img width="545" height="243" alt="image" src="https://github.com/user-attachments/assets/94b2a3a7-3bfc-45b5-8760-eff2441f2ae7" />


**Question 9**
---
<img width="824" height="334" alt="image" src="https://github.com/user-attachments/assets/854384fd-5713-4d11-a6b7-3cf0ac3dbe7a" />


```sql
SELECT product_id,original_price,discount_percentage,(original_price-(original_price*discount_percentage))as discounted_price
FROM Products ORDER BY discounted_price DESC LIMIT 3;

```

**Output:**

<img width="824" height="266" alt="image" src="https://github.com/user-attachments/assets/a71b9419-5ecb-427e-9f92-d65c1cb7f917" />


**Question 10**
---
<img width="816" height="385" alt="image" src="https://github.com/user-attachments/assets/3b5f65c4-25df-4005-b170-a26c3abb661e" />


```sql
SELECT EmployeeID,FirstName,BirthDate,(strftime('%Y','2023-12-30')-strftime('%Y',BirthDate))as age
FROM employees
where (strftime('%Y','2023-12-30')-strftime('%Y',BirthDate))>50;
```

**Output:**

<img width="847" height="573" alt="image" src="https://github.com/user-attachments/assets/504d7224-cbb5-4159-8308-4fadfe65c721" />

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
