
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

<img width="1277" height="627" alt="image" src="https://github.com/user-attachments/assets/4666df07-cdf8-4f60-ba1b-76107ae5427e" />


```sql
SELECT 
    c.cust_name,
    c.city AS city,
    c.grade,
    s.name AS Salesman,
    s.city AS city
FROM customer c
INNER JOIN salesman s
    ON c.salesman_id = s.salesman_id
WHERE c.grade < 300
ORDER BY c.customer_id ASC;
```

**Output:**

<img width="1282" height="836" alt="image" src="https://github.com/user-attachments/assets/39141b33-d945-4ce5-8d97-3de6e3df4eea" />


**Question 2**

<img width="1271" height="772" alt="image" src="https://github.com/user-attachments/assets/b07e7963-3e94-475b-ba13-c3380a681ef9" />


```sql
SELECT
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    c.cust_name,
    c.city AS customer_city,
    c.grade,
    s.name AS salesman_name,
    s.city AS salesman_city,
    s.commission
FROM orders o
INNER JOIN customer c
    ON o.customer_id = c.customer_id
INNER JOIN salesman s
    ON o.salesman_id = s.salesman_id;

```

**Output:**

<img width="1282" height="792" alt="image" src="https://github.com/user-attachments/assets/9952c47e-6cae-4d4a-a0d4-16361bb985c8" />



**Question 3**

<img width="1276" height="817" alt="image" src="https://github.com/user-attachments/assets/e6837e2f-d433-4755-a6c9-8584244ad5df" />


```sql
SELECT p.first_name, s.*
FROM patients p
INNER JOIN surgeries s
    ON p.patient_id = s.patient_id
WHERE p.discharge_date BETWEEN '2024-03-01' AND '2024-03-31'
  AND p.admission_date NOT BETWEEN '2024-03-01' AND '2024-03-31';

```

**Output:**
<img width="1296" height="505" alt="image" src="https://github.com/user-attachments/assets/387ff9ad-0f4d-49c5-9d79-84c027eecc3b" />


**Question 4**

<img width="1281" height="447" alt="image" src="https://github.com/user-attachments/assets/be6fb951-ed96-4c69-ba80-f80c16080b2b" />


```sql
SELECT
    c.cust_name,
    c.city,
    o.ord_no,
    o.ord_date,
    o.purch_amt
FROM customer c
LEFT JOIN orders o
    ON c.customer_id = o.customer_id
WHERE c.city = 'London';
```

**Output:**
<img width="1282" height="570" alt="image" src="https://github.com/user-attachments/assets/672450c8-8c4d-4dde-ac3e-97d259e949b9" />


**Question 5**

<img width="1221" height="692" alt="image" src="https://github.com/user-attachments/assets/45cb0f15-dba8-4b06-8510-754eb5b0b4dc" />


```sql
SELECT t.*
FROM test_results t
INNER JOIN patients p
    ON t.patient_id = p.patient_id
WHERE p.first_name = 'Alice';
```

**Output:**

<img width="1285" height="512" alt="image" src="https://github.com/user-attachments/assets/ba2ed2b8-cede-4c13-8486-c21eb6e3d685" />


**Question 6**

<img width="1277" height="630" alt="image" src="https://github.com/user-attachments/assets/26bb0c1e-94b2-43ac-b80a-ac85bf0b3139" />

```sql
SELECT
    c.cust_name,
    c.city AS city,
    c.grade,
    s.name AS Salesman,
    s.city AS city
FROM customer c
INNER JOIN salesman s
    ON c.salesman_id = s.salesman_id
ORDER BY c.customer_id ASC;

```

**Output:**

<img width="1286" height="590" alt="image" src="https://github.com/user-attachments/assets/7029ffad-cc9f-4a52-9a69-0d8c7c20041a" />


**Question 7**

<img width="1287" height="890" alt="image" src="https://github.com/user-attachments/assets/a55f42e9-156e-46c6-8af0-961f958f544c" />

```sql
SELECT
    c.cust_name AS "Customer Name",
    c.city AS city,
    s.name AS Salesman,
    s.city AS city,
    s.commission
FROM customer c
INNER JOIN salesman s
    ON c.salesman_id = s.salesman_id
WHERE c.city <> s.city
  AND s.commission > 0.12;
```

**Output:**
<img width="1297" height="727" alt="image" src="https://github.com/user-attachments/assets/a290c99f-0e55-4a4d-a2e0-5e07eff94695" />


**Question 8**

<img width="1261" height="640" alt="image" src="https://github.com/user-attachments/assets/75df8fd7-3634-442b-81bb-3e6487dec2b7" />


```sql
SELECT
    c.cust_name AS "Customer Name",
    c.city,
    s.name AS Salesman,
    s.commission
FROM customer c
INNER JOIN salesman s
    ON c.salesman_id = s.salesman_id
WHERE s.commission > 0.12;
```

**Output:**

<img width="1257" height="392" alt="image" src="https://github.com/user-attachments/assets/f3572b71-d7b9-4ec4-9d24-440789e79d7e" />


**Question 9**
<img width="1287" height="507" alt="image" src="https://github.com/user-attachments/assets/0e537776-d9cf-4984-9231-40250bc7739c" />


```sql
SELECT c.*
FROM customer c
LEFT JOIN orders o
    ON c.customer_id = o.customer_id
WHERE o.ord_date BETWEEN '2012-07-01' AND '2012-07-30';
```

**Output:**
<img width="1242" height="711" alt="image" src="https://github.com/user-attachments/assets/dad073a8-a0cb-45b2-9231-8851133d8896" />


**Question 10**

<img width="1297" height="511" alt="image" src="https://github.com/user-attachments/assets/4f73f5e7-038c-4807-87db-856eb96bd412" />

```sql
SELECT n.*
FROM nurses n
INNER JOIN departments d
    ON n.department_id = d.department_id
WHERE d.department_name = 'Pediatrics';
```

**Output:**
<img width="1297" height="511" alt="image" src="https://github.com/user-attachments/assets/2b0847f5-a3b2-4a2b-b94d-6dafe476cff4" />

## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
