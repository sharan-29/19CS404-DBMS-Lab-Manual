# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
<img width="865" height="386" alt="image" src="https://github.com/user-attachments/assets/2d7b540c-fc1e-4037-a66c-20db69152ef7" />


```sql
select * from Employee where age<(select avg(age) from employee where income>250000);
```

**Output:**

<img width="943" height="460" alt="image" src="https://github.com/user-attachments/assets/71c3e42a-56c7-496f-88e8-9a96a5ab090a" />


**Question 2**
---
<img width="848" height="427" alt="image" src="https://github.com/user-attachments/assets/d2dd6782-4014-4ed1-97cc-26fc37cd45f0" />


```sql
select * from grades g1 where grade=(select max(grade) from grades g2 where g2.subject=g1.subject);
```

**Output:**

<img width="860" height="438" alt="image" src="https://github.com/user-attachments/assets/521fb64a-b160-4791-98a8-f0fc0a00942d" />


**Question 3**
---
<img width="794" height="451" alt="image" src="https://github.com/user-attachments/assets/66ffd31b-67ca-48d5-ba65-d464ddf8b382" />


```sql
select o.ord_no,o.purch_amt,o.ord_date,o.customer_id,o.salesman_id from orders o join salesman s 
on o.salesman_id=s.salesman_id where s.name='Paul Adam';
```

**Output:**

<img width="859" height="400" alt="image" src="https://github.com/user-attachments/assets/877f303d-511f-4107-8cd3-2e17a82ea251" />


**Question 4**
---
<img width="848" height="374" alt="image" src="https://github.com/user-attachments/assets/07e3718b-f449-4f69-ab81-c87b0d7e90f9" />


```sql
select * from orders where purch_amt>(select avg(purch_amt) from orders where ord_date='2012-10-10');
```

**Output:**

<img width="871" height="426" alt="image" src="https://github.com/user-attachments/assets/ef1989a0-2ffa-48ce-b95c-192b1ab684ea" />


**Question 5**

---
<img width="854" height="350" alt="image" src="https://github.com/user-attachments/assets/1cf4c6e5-0458-4522-a7ee-66b2cc53cc47" />


```sql
select * from employee where age<(select avg(age) from employee where income>1000000);
```


**Output:**

<img width="860" height="390" alt="image" src="https://github.com/user-attachments/assets/0e696b3e-8097-4b5f-9ce0-38eac5a5e1db" />


**Question 6**
---
<img width="833" height="586" alt="image" src="https://github.com/user-attachments/assets/3a34ea34-ba59-464b-9a4f-405c70bf500c" />


```sql
select name,city from customer where city in(select city from customer where id in(3,7));
```

**Output:**

<img width="629" height="423" alt="image" src="https://github.com/user-attachments/assets/3dd26e33-9983-4601-a8fa-a4e3279b82d9" />


**Question 7**
---
<img width="846" height="366" alt="image" src="https://github.com/user-attachments/assets/e29e156e-8055-4d75-a4b1-03ea8ac09ea6" />


```sql
select s.salesman_id,s.name from salesman s join customer c on s.salesman_id=c.salesman_id
group by s.salesman_id,s.name having count(c.salesman_id)>1;
```

**Output:**

<img width="603" height="429" alt="image" src="https://github.com/user-attachments/assets/638e5009-8ac4-4767-81f9-3cc7e467829c" />


**Question 8**
---
<img width="886" height="433" alt="image" src="https://github.com/user-attachments/assets/ba27cfbe-024e-4a71-94af-296e5893a51b" />

```sql
select * from grades g1 where grade=(select min(grade) from grades g2 where g2.subject=g1.subject); 
```

**Output:**

<img width="839" height="446" alt="image" src="https://github.com/user-attachments/assets/fa443989-aaea-4ecf-ba75-b9be4d2f15b4" />


**Question 9**
---
<img width="801" height="452" alt="image" src="https://github.com/user-attachments/assets/46e8a152-fa22-46dd-b45c-3d88f18f2e02" />


```sql
select * from customers where salary>4500;
```

**Output:**

<img width="722" height="456" alt="image" src="https://github.com/user-attachments/assets/7fde9536-9528-44ca-9aaf-41663281bc9c" />


**Question 10**
---
<img width="824" height="488" alt="image" src="https://github.com/user-attachments/assets/c412ba40-409d-494e-9990-06e9cd7f21c5" />


```sql
select * from customers where salary>1500;
```

**Output:**

<img width="904" height="531" alt="image" src="https://github.com/user-attachments/assets/31d27400-5349-4159-879e-2e037b1441a6" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
