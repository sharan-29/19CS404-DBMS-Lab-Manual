# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--

<img width="994" height="422" alt="image" src="https://github.com/user-attachments/assets/1ae3259e-ad46-4680-b9b1-b2a21c78e670" />



```sql
create table Events(EventID INTEGER,EventName TEXT,EventDate DATE);
```

**Output:**

<img width="1223" height="446" alt="image" src="https://github.com/user-attachments/assets/7bf790f9-18fd-44d0-9378-9d25a1c033f9" />


**Question 2**
---
<img width="857" height="391" alt="image" src="https://github.com/user-attachments/assets/ac0d0b84-dccb-4946-ba6f-ce34792b101d" />


```sql
insert into Employee(EmployeeID,Name,Position,Department,Salary)values(2,'John Smith','Developer','IT',75000),(3,'Anna Bell','Designer','Marketing',68000);
```

**Output:**

<img width="1232" height="434" alt="image" src="https://github.com/user-attachments/assets/667cb16c-815c-4c45-ae8f-0fcd8fb8b135" />


**Question 3**
---
<img width="1222" height="457" alt="image" src="https://github.com/user-attachments/assets/e6d76ebd-c475-4a26-8601-5811d67ff0c3" />


```sql
create table item(
item_id TEXT PRIMARY KEY,item_desc TEXT NOT NULL,rate INTEGER NOT NULL,icom_id TEXT(4),FOREIGN KEY(icom_id)REFERENCES company(com_id) ON UPDATE SET NULL ON DELETE SET NULL);
```

**Output:**

<img width="874" height="426" alt="image" src="https://github.com/user-attachments/assets/4beaa882-65a8-4a12-96e8-b7bf5970b489" />


**Question 4**
---
<img width="858" height="312" alt="image" src="https://github.com/user-attachments/assets/48ff6e4f-beb3-4c15-b4bc-7fb3e1ee4aed" />


```sql
insert into Student_details(RollNo,Name,Gender,Subject,MARKS)values(201,'David Lee','M','Physics',92);
```

**Output:**

<img width="870" height="323" alt="image" src="https://github.com/user-attachments/assets/c90db6fe-b556-4507-beff-82b2314209dd" />


**Question 5**
---
<img width="857" height="443" alt="image" src="https://github.com/user-attachments/assets/03e32da0-1ed7-4938-8451-92a3d480be47" />


```sql
create table Customers(CustomerID INTEGER,Name TEXT,Email TEXT,JoinDate DATETIME);
```

**Output:**

<img width="869" height="472" alt="image" src="https://github.com/user-attachments/assets/04a810e4-132a-4bef-bd88-7e9f26fbe849" />


**Question 6**
---
<img width="851" height="290" alt="image" src="https://github.com/user-attachments/assets/c1026aaa-a637-4da2-b9f1-3f3c22c095cf" />


```sql
alter table Student_details add column Email VARCHAR(50);
alter table Student_details add column MARKS INTEGER DEFAULT 0;
```

**Output:**

<img width="882" height="317" alt="image" src="https://github.com/user-attachments/assets/35974365-8ee6-4725-a2bf-000798b86c0b" />


**Question 7**
---
<img width="871" height="393" alt="image" src="https://github.com/user-attachments/assets/9042c81e-246d-49e5-b32e-ac3971f0b8a0" />


```sql
alter table employee add column first_name varchar(50);
alter table employee add column last_name varchar(50);
```

**Output:**

<img width="868" height="386" alt="image" src="https://github.com/user-attachments/assets/92392fc4-b642-4830-9b9c-7a1c00c0e038" />


**Question 8**
---
<img width="865" height="396" alt="image" src="https://github.com/user-attachments/assets/9e95c313-7884-4be5-8861-c85ba970c08a" />


```sql
create table Shipments (
ShipmentID INTEGER PRIMARY KEY,ShipmentDate DATE,SupplierID INTEGER,OrderID INTEGER,FOREIGN KEY(SupplierID)REFERENCES Suppliers(SupplierID),FOREIGN KEY(OrderID)REFERENCES Orders(OrderID));
```

**Output:**

<img width="875" height="330" alt="image" src="https://github.com/user-attachments/assets/cbba4170-4266-4d79-8692-906fd36a66f3" />


**Question 9**
---
<img width="874" height="515" alt="image" src="https://github.com/user-attachments/assets/540f09eb-002d-4083-bde1-67ef4e1a93e1" />


```sql
INSERT INTO Student_details(RollNo,Name,Gender)values(204,'Samuel Black','M');
```

**Output:**

<img width="876" height="414" alt="image" src="https://github.com/user-attachments/assets/a8272b84-30bc-4809-a65a-f2ff0bbc4065" />


**Question 10**
---
<img width="864" height="463" alt="image" src="https://github.com/user-attachments/assets/58fb265c-6479-4f4f-8e57-f6891854edcc" />


```sql
create table Locations(LocationID INTEGER,LocationName TEXT,Address TEXT);
```

**Output:**

<img width="853" height="350" alt="image" src="https://github.com/user-attachments/assets/5cec2d15-5b59-4f1c-9427-4b82844b44d0" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
