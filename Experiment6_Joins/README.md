# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
<img width="858" height="785" alt="image" src="https://github.com/user-attachments/assets/32bfcc09-d4ef-4674-89c0-da79b7bc8b7b" />


```sql
select c.cust_name,c.city,o.ord_no,o.ord_date,o.purch_amt as "Order Amount"
from customer c LEFT JOIN orders o on c.customer_id = o.customer_id order by o.ord_date ASC;
```

**Output:**

<img width="859" height="743" alt="image" src="https://github.com/user-attachments/assets/fa994e02-c34b-46a3-82da-bd5703b796ce" />


**Question 2**
---
<img width="849" height="519" alt="image" src="https://github.com/user-attachments/assets/6863ae70-9988-44e0-a202-f846d86bab93" />


```sql
select n.nurse_id,d.department_name from nurses n INNER JOIN departments d ON n.department_id=d.department_id where
n.first_name='David' and n.last_name='Moore';
```

**Output:**

<img width="777" height="317" alt="image" src="https://github.com/user-attachments/assets/11c6f24e-dda6-4317-9d88-1e1478fabf12" />

**Question 3**
---
<img width="868" height="664" alt="image" src="https://github.com/user-attachments/assets/4ec7ed4e-13d9-4655-89a3-eacbf81ecd6f" />


```sql
select c.* from customer c left join orders o on c.customer_id=o.customer_id where o.ord_date between '2012-08-01' 
and '2012-08-30';
```

**Output:**

<img width="808" height="456" alt="image" src="https://github.com/user-attachments/assets/0e1db26a-d671-4b2e-b633-f1487dbd6b54" />

**Question 4**
---
<img width="855" height="495" alt="image" src="https://github.com/user-attachments/assets/8e254cb8-f701-437d-9e69-80c073de577d" />


```sql
select p.* from patients p INNER JOIN test_results tr ON p.patient_id=tr.patient_id 
where tr.test_name='X-Ray' and tr.result='Normal';
```

**Output:**

<img width="928" height="454" alt="image" src="https://github.com/user-attachments/assets/e7bf8def-85fc-4000-83c6-f6b05d2630b2" />


**Question 5**
---
<img width="848" height="627" alt="image" src="https://github.com/user-attachments/assets/a05e8f69-898f-4a36-8616-5829a288a456" />


```sql
select p.first_name ,s.* from patients p inner join surgeries s on p.patient_id=s.patient_id where p.first_name='Alice';
```

**Output:**

<img width="875" height="403" alt="image" src="https://github.com/user-attachments/assets/583f1326-d164-4ab6-ad30-0d038dcbaebc" />


**Question 6**
---
<img width="840" height="488" alt="image" src="https://github.com/user-attachments/assets/55b4ca9b-1e52-4008-8669-3ee37bab6bd2" />

```
SELECT c.cust_name, c.city, o.ord_no, o.ord_date, o.purch_amt
FROM customer c
LEFT JOIN orders o
ON c.customer_id = o.customer_id
WHERE c.city = 'London';
```

**Output:**

<img width="870" height="458" alt="image" src="https://github.com/user-attachments/assets/23b4877a-a395-440c-9ac0-4645e3303d63" />


**Question 7**
---
<img width="825" height="508" alt="image" src="https://github.com/user-attachments/assets/bc01af03-04b6-4e73-b73f-250bd4e05eee" />


```sql
SELECT p.first_name AS patient_name, d.first_name AS doctor_name
FROM patients p
INNER JOIN doctors d
ON p.doctor_id = d.doctor_id
WHERE p.date_of_birth > '1990-01-01';
```

**Output:**

![Screenshot](join8.png)

**Question 8**
---
![Screenshot](join8que.png)

```sql
SELECT t.*
FROM test_results t
INNER JOIN patients p
ON t.patient_id = p.patient_id
WHERE p.first_name = 'Alice';
```

**Output:**

![Screenshot](8ans.png)

**Question 9**
---
![Screenshot](9que.png)

```sql
SELECT p.first_name AS patient_name, a.*
FROM patients p
INNER JOIN appointments a
ON p.patient_id = a.patient_id;
```

**Output:**

![Screenshot](9ans.png)

**Question 10**
---
![Screenshot](10que.png)

```sql
SELECT c.cust_name, s.name
FROM customer c
LEFT JOIN salesman s
ON c.salesman_id = s.salesman_id
WHERE c.city = s.city;
```

**Output:**

![Screenshot](10ans.png)


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
