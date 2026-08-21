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
<img width="1298" height="253" alt="image" src="https://github.com/user-attachments/assets/5d5153e9-b768-453f-b4dc-e96926acf040" />


```sql
SELECT
    product_id,
    original_price,
    discount_percentage,
    original_price * (1-discount_percentage) AS discounted_price,
    CAST((1-discount_percentage)*100 AS INT) || '%' AS discounted_price_percentage
FROM products;
```

**Output:**

<img width="1271" height="251" alt="image" src="https://github.com/user-attachments/assets/492a91aa-0c3d-4c2c-b701-87d7aacf4116" />


**Question 2**
---
<img width="545" height="362" alt="image" src="https://github.com/user-attachments/assets/855bd6af-23f2-4362-a083-c777746a34d5" />


```sql
SELECT ename FROM emp WHERE ename LIKE 'S____';
```

**Output:**

<img width="281" height="273" alt="image" src="https://github.com/user-attachments/assets/6780a65e-792a-4a18-8f2d-8a0034f83f28" />


**Question 3**
---
<img width="1087" height="371" alt="image" src="https://github.com/user-attachments/assets/c11c852a-9f75-4aa0-8ad6-7fc07efb3477" />


```sql
DELETE FROM customer WHERE CUST_NAME LIKE '%Holmes%';
```

**Output:**

<img width="1758" height="330" alt="image" src="https://github.com/user-attachments/assets/668723b1-4507-4a6a-94e9-7dccb67c8964" />


**Question 4**
---
<img width="768" height="533" alt="image" src="https://github.com/user-attachments/assets/5a51a37c-592e-4171-a9f9-a5022652636f" />


```sql
SELECT * FROM emp WHERE strftime('%Y',hiredate)='2022';
```

**Output:**

<img width="1577" height="347" alt="image" src="https://github.com/user-attachments/assets/85d73b6b-914e-4f86-b6d5-56417fce8ce8" />


**Question 5**
---
<img width="737" height="263" alt="image" src="https://github.com/user-attachments/assets/a8a39c67-6b4b-4789-a8be-b20a392de2e7" />

```sql
UPDATE Products SET quantity=quantity*1.1;
```

**Output:**

<img width="1456" height="450" alt="image" src="https://github.com/user-attachments/assets/43888bd9-f4b7-4cf7-9f83-287308c48fe4" />


**Question 6**
---
<img width="636" height="367" alt="image" src="https://github.com/user-attachments/assets/48998a3b-d8c8-4e62-b649-b95dad75706c" />


```sql
UPDATE Products SET reorder_lvl=40 WHERE category='Grocery';
```

**Output:**

<img width="1856" height="345" alt="image" src="https://github.com/user-attachments/assets/feaf4cbc-42a8-415c-95cc-1edcb9f6dd2b" />


**Question 7**
---
<img width="1220" height="383" alt="image" src="https://github.com/user-attachments/assets/41b9fe1d-4ea7-4152-b898-938a33e2cb1c" />


```sql
DELETE FROM customer WHERE CUST_CITY !='New York' AND OUTSTANDING_AMT>5000;
```

**Output:**

<img width="1858" height="396" alt="image" src="https://github.com/user-attachments/assets/d64b49fa-b5b4-4620-9273-cd336c886211" />


**Question 8**
---
<img width="518" height="486" alt="image" src="https://github.com/user-attachments/assets/3912dc6f-92f4-4b9f-85d4-31c2e4892ff4" />


```sql
UPDATE sales SET sell_price=sell_price+3
WHERE product_id IN(
    SELECT product_id FROM products WHERE supplier_id=4
);
```

**Output:**

<img width="1177" height="262" alt="image" src="https://github.com/user-attachments/assets/e88d2b3d-271b-420c-bbec-dfe929c47b1d" />


**Question 9**
---
<img width="778" height="370" alt="image" src="https://github.com/user-attachments/assets/5dc29c52-07e3-4457-a1f2-221becf4fff5" />


```sql
SELECT
    product_id,
    original_price,
    discount_percentage,
    original_price*(1-discount_percentage) AS discounted_price
FROM Products ORDER BY discounted_price DESC LIMIT 3;
```

**Output:**

<img width="806" height="212" alt="image" src="https://github.com/user-attachments/assets/141fb04e-43fe-49aa-bce5-f78a26d050bc" />


**Question 10**
---
<img width="1212" height="435" alt="image" src="https://github.com/user-attachments/assets/4b847add-1b71-4d26-b979-fac1c9fc8edb" />


```sql
UPDATE Employees SET first_name='John' WHERE department_id='80' AND commission_pct<0.35;
```

**Output:**

<img width="1691" height="295" alt="image" src="https://github.com/user-attachments/assets/02a99bef-43e9-4ba4-9725-4f0c4f32bc71" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
