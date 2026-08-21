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
<img width="1097" height="287" alt="image" src="https://github.com/user-attachments/assets/02d23506-648a-462f-bfaf-fe5271f22b32" />


```sql
ALTER TABLE employee ADD COLUMN first_name varchar(50);
ALTER TABLE employee ADD COLUMN last_name varchar(50);
```

**Output:**

<img width="1005" height="216" alt="image" src="https://github.com/user-attachments/assets/55b0355d-d80d-45d7-9308-f4bb73757c20" />

**Question 2**
---
<img width="615" height="268" alt="image" src="https://github.com/user-attachments/assets/3496520d-4946-42b9-a1d2-07aa56cbcbd3" />


```sql
CREATE TABLE item (
    item_id TEXT PRIMARY KEY,
    item_desc TEXT NOT NULL,
    rate INTEGER NOT NULL,
    icom_id TEXT CHECK(length(icom_id) <= 4),
    FOREIGN KEY (icom_id) REFERENCES company(com_id)
        ON UPDATE SET NULL
        ON DELETE SET NULL
);
```

**Output:**

<img width="918" height="237" alt="image" src="https://github.com/user-attachments/assets/4d48249b-3872-4e3a-99f2-883bd2d7794e" />


**Question 3**
---
<img width="800" height="291" alt="image" src="https://github.com/user-attachments/assets/05f7dd48-2cf8-4d66-8870-ff88a5627e4f" />


```sql
CREATE TABLE products (
    product_id INTEGER PRIMARY KEY,
    product_name TEXT NOT NULL,
    list_price DECIMAL(10, 2) NOT NULL,
    discount DECIMAL(10, 2) NOT NULL DEFAULT 0,
    CHECK (list_price >= discount AND discount >= 0 AND list_price >= 0)
);
```

**Output:**

<img width="1197" height="202" alt="image" src="https://github.com/user-attachments/assets/603f0135-d6af-42f1-8bbe-857f661edd3e" />

**Question 4**
---
<img width="1121" height="248" alt="image" src="https://github.com/user-attachments/assets/7bbb7746-6d4a-4610-81ad-757353d7ae02" />


```sql
CREATE TABLE contacts (
    contact_id INTEGER PRIMARY KEY,
    first_name TEXT NOT NULL,
    last_name TEXT NOT NULL,
    email TEXT,
    phone TEXT NOT NULL CHECK (length(phone) >= 10)
);
```

**Output:**

<img width="1692" height="246" alt="image" src="https://github.com/user-attachments/assets/700edd55-2acb-4b52-9ce0-b9adfaf8d4df" />


**Question 5**
---
<img width="636" height="267" alt="image" src="https://github.com/user-attachments/assets/ced3c408-25cd-4e85-b46f-2fe44c3856e1" />


```sql
Create Table Members(
    MemberID INTEGER,
    MemberName TEXT,
    JoinDate DATE
);
```

**Output:**

<img width="1253" height="272" alt="image" src="https://github.com/user-attachments/assets/a01a945d-3a62-438b-9a39-96fe998bba0f" />


**Question 6**
---
<img width="947" height="232" alt="image" src="https://github.com/user-attachments/assets/1e8ac123-2c58-4b20-a6f4-471182da136e" />


```sql
create table Department(
    DepartmentID INTEGER PRIMARY KEY,
    DepartmentName TEXT UNIQUE NOT NULL,
    Location TEXT
);
```

**Output:**

<img width="1552" height="221" alt="image" src="https://github.com/user-attachments/assets/002d2b69-af3d-4fd8-9241-4e48ef582685" />


**Question 7**
---
<img width="807" height="172" alt="image" src="https://github.com/user-attachments/assets/10c65d4a-d574-40d9-a642-429b763b8049" />


```sql
INSERT INTO Products (ProductID, Name, Category) VALUES (104, 'Tablet', 'Electronics');
```

**Output:**

<img width="1075" height="192" alt="image" src="https://github.com/user-attachments/assets/b7225d60-98e3-4f52-aa93-f4183de54e1c" />


**Question 8**
---
<img width="770" height="166" alt="image" src="https://github.com/user-attachments/assets/85a052ac-787b-4a92-a7e9-938868768bb2" />


```sql
Insert into Customers VALUES (301,'Michael Jordan','123 Maple St','Chicago',60616);
```

**Output:**

<img width="1140" height="190" alt="image" src="https://github.com/user-attachments/assets/291cb92c-b228-48ca-bdbd-36774564620e" />


**Question 9**
---
<img width="677" height="311" alt="image" src="https://github.com/user-attachments/assets/c3130608-29e1-45b6-ae1b-89feb859ae6a" />


```sql
Insert into Student_details (RollNo,Name,Gender) VALUES (204,'Samuel Black','M');
```

**Output:**

<img width="765" height="240" alt="image" src="https://github.com/user-attachments/assets/3a9bd048-47b6-4d08-8885-68b1fd5fa487" />


**Question 10**
---
<img width="956" height="200" alt="image" src="https://github.com/user-attachments/assets/f9b38618-1d74-4925-9c48-8d426ae1a29b" />


```sql
ALTER TABLE Student_details ADD COLUMN email TEXT NOT NULL DEFAULT 'Invalid';
```

**Output:**

<img width="1042" height="196" alt="image" src="https://github.com/user-attachments/assets/f606db04-188b-4c20-8163-bde70af4be23" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
