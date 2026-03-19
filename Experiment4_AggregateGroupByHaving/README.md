# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
<img width="816" height="356" alt="image" src="https://github.com/user-attachments/assets/8ae8205f-f70b-46d7-8050-0dd670bf8242" />

```sql
select sum(inventory) as total_available_amount from fruits where price>0.5;
```

**Output:**

<img width="768" height="332" alt="image" src="https://github.com/user-attachments/assets/be0b58ae-7c84-4b49-bbb7-d7743f1365bd" />


**Question 2**
---
<img width="770" height="314" alt="image" src="https://github.com/user-attachments/assets/b4f1f64b-a2ec-4621-8168-9cb7a4fe4c0e" />


```sql
select COUNT(customer_id) AS COUNT from customer;
```

**Output:**

<img width="649" height="337" alt="image" src="https://github.com/user-attachments/assets/79652eaa-0923-4abc-9b1a-e98baf8b52c4" />


**Question 3**
---
<img width="782" height="316" alt="image" src="https://github.com/user-attachments/assets/e526bd46-05da-4ae0-9788-fa4c6116a08f" />


```sql
select count(distinct(salesman_id)) as COUNT from orders;
```

**Output:**

<img width="414" height="257" alt="image" src="https://github.com/user-attachments/assets/2138fbbf-8809-4d21-b5fa-162ca80b74ca" />

**Question 4**
---
<img width="870" height="269" alt="image" src="https://github.com/user-attachments/assets/4cd026f7-c0f4-4b8b-9618-eef1b87a7a23" />


```sql
SELECT Specialty ,Gender,count(*) as TotalDoctors from Doctors group by Specialty,Gender;
```

**Output:**

<img width="711" height="392" alt="image" src="https://github.com/user-attachments/assets/8e87a555-e0eb-4f33-a672-04e7a27a2db6" />


**Question 5**
---
<img width="860" height="529" alt="image" src="https://github.com/user-attachments/assets/624092af-a8a4-46a8-82f8-c219f2df2c89" />


```sql
SELECT Frequency ,count(Frequency) as TotalPrescriptions from Prescriptions group by Frequency;
```

**Output:**

<img width="784" height="481" alt="image" src="https://github.com/user-attachments/assets/225f648a-89bc-45aa-a19c-cf2db8f989f2" />


**Question 6**
---
<img width="912" height="307" alt="image" src="https://github.com/user-attachments/assets/0a0ebe32-d0f7-4aed-bd4c-76fadf094ca5" />


```sql
select strftime('%Y-%m',Date) as Month ,count(*) as TotalRecords from MedicalRecords group by Month;
```

**Output:**

<img width="741" height="415" alt="image" src="https://github.com/user-attachments/assets/453e89b1-afb6-45e7-86e8-7e5a7bcc2c5b" />

**Question 7**
---
<img width="891" height="341" alt="image" src="https://github.com/user-attachments/assets/5408419c-8883-42a1-b88e-97ba321b4f0d" />


```sql
select age,MAX(income) from employee group by age having MAX(income)>2000000;
```

**Output:**

<img width="823" height="407" alt="image" src="https://github.com/user-attachments/assets/196d7f14-cb81-43b9-9771-d6cbd3786f52" />


**Question 8**
---
<img width="849" height="346" alt="image" src="https://github.com/user-attachments/assets/04f2bae6-8b3e-42cc-be85-8f40990f95ce" />


```sql
SELECT jdate ,MAX(workhour) from employee1 group by jdate having MAX(workhour)>12;
```

**Output:**

<img width="644" height="313" alt="image" src="https://github.com/user-attachments/assets/b9d75c86-0a43-415c-8146-22cd04bc4029" />


**Question 9**
---
<img width="831" height="338" alt="image" src="https://github.com/user-attachments/assets/279f6ee8-a7a6-42b8-8f3b-e3c488c1641c" />

```sql
select address,SUM(salary) from customer1 group by address having SUM(salary)>2000;
```

**Output:**

<img width="736" height="318" alt="image" src="https://github.com/user-attachments/assets/58690290-5b2f-4541-9815-3f7f6f77255b" />


**Question 10**
---
<img width="807" height="329" alt="image" src="https://github.com/user-attachments/assets/8c6968e8-9217-483c-80f2-ceba44476b43" />


```sql
select jdate , MIN(workhour) from employee1 group by jdate having MIN(workhour)<10;
```

**Output:**

<img width="632" height="370" alt="image" src="https://github.com/user-attachments/assets/9e096d41-5ce5-4059-a4c7-ca3a1b1340fd" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
