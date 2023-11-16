# 1.comparative study of various database management systems
Here's a list of various types of Database Management Systems (DBMS) 

markdown
## Database Management Systems

### Relational Database Management Systems (RDBMS)

- MySQL
- PostgreSQL
- Oracle Database
- Microsoft SQL Server
- SQLite

### NoSQL Database Management Systems

- MongoDB (document-oriented)
- Cassandra (wide-column store)
- Redis (key-value store)
- Neo4j (graph database)
- CouchDB (document-oriented)

### Object-Oriented Database Management Systems (OODBMS)

- db4o
- ObjectDB

### NewSQL Database Management Systems

- Google Spanner
- CockroachDB
- NuoDB

### In-Memory Database Management Systems

- Redis (can also be classified as NoSQL)
- Memcached

### Columnar Database Management Systems

- Apache HBase
- Amazon Redshift

### Time-Series Database Management Systems

- InfluxDB
- OpenTSDB

### Graph Database Management Systems

- Neo4j
- Amazon Neptune

# 2. Data Definition Language (DDL), Data Manipulation Language (DML), and Data Control 
Language (DCL)
| Data Definition Language (DDL) | Description                                               | Example                                      |
|-------------------------------|-----------------------------------------------------------|----------------------------------------------|
| CREATE                        | Defines new database objects such as tables, indexes, etc. | CREATE TABLE users (id INT PRIMARY KEY, username VARCHAR(50) NOT NULL, email VARCHAR(100) UNIQUE);` |
| ALTER                         | Modifies the structure of an existing database object.    | `ALTER TABLE users ADD COLUMN birthdate DATE; |
| DROP                          | Deletes a database object (e.g., table, index).           | `DROP TABLE users;                          |

| Data Manipulation Language (DML) | Description                                   | Example                                        |
|----------------------------------|-----------------------------------------------|------------------------------------------------|
| SELECT                           | Retrieves data from one or more tables.      | SELECT * FROM users WHERE age > 21;`           |
| INSERT                           | Adds new records into a table.               | `INSERT INTO users (username, email) VALUES ('JohnDoe', 'john@example.com'); |
| UPDATE                           | Modifies existing records in a table.        | `UPDATE users SET age = 25 WHERE username = JohnDoe; |
| DELETE                           | Removes records from a table.                | `DELETE FROM users WHERE username = JohnDoe'; |

| Data Control Language (DCL) | Description                                | Example                                           |
|-----------------------------|--------------------------------------------|---------------------------------------------------|
| GRANT                       | Provides specific privileges to users.     | GRANT SELECT, INSERT ON users TO employee_role;` |
| REVOKE                      | Withdraws previously granted permissions. | REVOKE INSERT ON users FROM employee_role;`      |
| DENY                        | Explicitly denies certain permissions.      | DENY DELETE ON users TO temporary_user;`         |
# 3. How to apply Constraints at various levels.
## Constraints in Database Design

### Table-Level Constraints

### 1. primary key
A primary key is a column or set of columns in a relational database table that uniquely identifies each row in the table. 

example :-

creating table with primary key and inserting values in it :-

![WhatsApp Image 2023-11-16 at 5 48 13 PM](https://github.com/ankit35136/rdbms-practical2/assets/146933815/16db34aa-39df-4efc-a969-67d1debf0d77)

OUtput :-

![image](https://github.com/ankit35136/rdbms-practical2/assets/146933815/05ee512e-89e4-47f1-86fc-ef092b249d7c)


### 2. foreign key

creating table with primary key and foreign key and inserting values in it :-

![image](https://github.com/ankit35136/rdbms-practical2/assets/146933815/287b7075-4870-4ae9-b5a0-688aace11f43)


OUtput after the execution :-

![image](https://github.com/ankit35136/rdbms-practical2/assets/146933815/c8f08c52-74d2-4e7c-a92c-73cf0b238e25)

### 3. unique key

creating a table with unique key :-

![image](https://github.com/ankit35136/rdbms-practical2/assets/146933815/f28070e3-35c7-4954-ab5d-7f1aa5ed8873)


inserting values in it :-

![image](https://github.com/ankit35136/rdbms-practical2/assets/146933815/49f39a18-c910-490e-a207-acc465730c5c)


Output :-

![image](https://github.com/ankit35136/rdbms-practical2/assets/146933815/71fb0e3d-1c6e-485d-b381-ab2192ddc72d)


### check constraints on table level :-
creating table with check constraints :-

![Screenshot 2023-11-14 150703](https://github.com/aman7935/rdbms-practical/assets/146933698/115ba7cc-dc37-46df-afde-de176da9d9c4)

if we enter the age less than 18 it will show error

![Screenshot 2023-11-14 151150](https://github.com/aman7935/rdbms-practical/assets/146933698/2bd805dc-efc4-4fc9-a4f3-98177696aed5)


## Column-Level Constraints
### 1. NOT NULL constraints :-

![Screenshot 2023-11-14 151715](https://github.com/aman7935/rdbms-practical/assets/146933698/2ea7f20e-e244-43f7-ac25-5c619bdbbcae)

A NOT NULL constraint in SQL is a rule that prevents NULL values from being entered into a column within a table. This means that you should provide a valid SQL NOT NULL value to that column in the INSERT or UPDATE statements, as the column will always contain data.

### 2. DEFAULT constraints :-

![Screenshot 2023-11-14 154224](https://github.com/aman7935/rdbms-practical/assets/146933698/bdd25f17-ba86-445c-8f39-cbec953868b3)

it helps to print the values which we declare with DEFAULT keywords.

![Screenshot 2023-11-14 154347](https://github.com/aman7935/rdbms-practical/assets/146933698/73ef0243-1eab-46d5-a122-53dd5af2f5bb)


# 4. View data in the required form using Operators, Functions and Joins.
## Using SQL Operators

Operators are used for operations like arithmetic, comparison, and logical operations.

### 1.Filtering data with WHERE clause

![image](https://github.com/ankit35136/rdbms-practical2/assets/146933815/a28faf8e-950b-4ab3-a521-15f7a4b4f843)

it will show the values in which the salary in employees table is greater than 50000.

### 2.Logical operator

![image](https://github.com/ankit35136/rdbms-practical2/assets/146933815/1d260284-7ccb-4aed-89b1-a3f42b083635)

it will print only values in which the salary is greater than 50000 or with the city name ludhiana.

### 3.Mathematical operator(perform mathematical operator on numeric columns)

![image](https://github.com/ankit35136/rdbms-practical2/assets/146933815/1e349a86-26cc-4962-813c-1d6cc7a19678)


this operators is used when want to multipy the values in columns with specific value. These only can perform numeric functons. There some other opertors like 
(addition, subtraction, division, modulus) with the same syntax. 

## using functions 
1*String Functions:*
   - CONCAT : Concatenate two or more strings.
   - UPPER and LOWER : Convert a string to uppercase or lowercase.
   - SUBSTRING or SUBSTR : Extract a substring from a string.
   - LENGTH or LEN : Get the length of a string.
   - TRIM: Remove leading and trailing spaces.

2. *Numeric Functions:*
   - SUM, AVG, MIN, MAX : Aggregate functions for sum, average, minimum, and maximum values

3. *Conversion Functions:*
   - CAST or CONVERT: Convert data types.
   - TO_DATE or TO_NUMBER : Convert strings to date or number types.
     
### Using Joins
Join clause use combine rows from two or more table, based on a related column between them

1. Inner join(Inner joins combine records from two tables whenever there are matching values in a field common to both tables)

 ![image](https://github.com/aman7935/rdbms-practical/assets/146933698/59328fe0-0838-4582-af2e-adf7d1f8ccf5)

![image](https://github.com/ankit35136/rdbms-practical2/assets/146933815/b100d4c5-c0fe-455b-9f20-3fa0b217435e)

2. left join(LEFT JOIN , also called LEFT OUTER JOIN , returns all records from the left (first) table and the matched records from the right (second) table.)

![image](https://github.com/ankit35136/rdbms-practical2/assets/146933815/39be9c98-56cf-465a-a2d1-72e65266b03d)


3. Right join(The RIGHT JOIN command returns all rows from the right table, and the matching records from the left table. The result is NULL from the left side, when there is no match.)

![image](https://github.com/ankit35136/rdbms-practical2/assets/146933815/aed1a74b-3347-4f06-b2f7-1330aafa602a)


4. full join(FULL JOIN creates the result-set by combining results of both LEFT JOIN and RIGHT JOIN)

![Screenshot 2023-11-14 172422](https://github.com/aman7935/rdbms-practical/assets/146933698/82e443e8-2150-4a75-a91a-b5d0c5cd0f95)

Output :-

![image](https://github.com/aman7935/rdbms-practical/assets/146933698/aa483ddd-7399-4c6e-a6ea-faa0f4fa1e61)

#5. Creating different types of Views for tailored presentation of data
1. **Simple View:**

   ![image](https://github.com/aman7935/rdbms-practical/assets/146933698/0b583aca-4609-475a-95d2-0c68203a34ff)


2. **Complex View:**

  ![image](https://github.com/aman7935/rdbms-practical/assets/146933698/4af23099-6481-47a4-9604-76443db7861c)


3. **Materialized View:**

  ![image](https://github.com/aman7935/rdbms-practical/assets/146933698/fe74d131-a93d-4aa5-9e86-08da84fcf369)

4. **Indexed View:**

  ![image](https://github.com/aman7935/rdbms-practical/assets/146933698/bc51dc3b-af87-45ea-84c5-83d675ac3a60)

when we create a view, the view does not store any data by default. So, when we query a view, it actually queries the underlying base table and gets the data. But we can change this default behavior in SQL Server i.e. the SQL Server Views can store the data physically.

# 6. How to apply Conditional Controls in PL/SQL

## there are two types of condition control statements(IF statement and CASE statements)
### IF statements can be further divided into 3 parts
1. IF-THEN

example :-

![image](https://github.com/ankit35136/rdbms-practical2/assets/146933815/7018fbdb-bce9-4233-82b7-440c0e79d352)

2. IF-THEN-ELSE

example :-

![Screenshot 2023-11-16 172808](https://github.com/ankit35136/rdbms-practical2/assets/146933815/b50f120f-2054-4899-94b6-2275a1841112)


3. IF-THEN-ELSIF

example :-

![Screenshot 2023-11-16 173004](https://github.com/ankit35136/rdbms-practical2/assets/146933815/6fc99562-030c-4387-b085-d9b7d7168ca1)

## 2. CASE STATEMENT

EXAMPLE :-

![Screenshot 2023-11-16 173135](https://github.com/ankit35136/rdbms-practical2/assets/146933815/be0d5edc-237f-4a8a-a0d9-f9b0b4c1c875)

## SEARCHED CASE STATEMENT
![Screenshot 2023-11-16 173338](https://github.com/ankit35136/rdbms-practical2/assets/146933815/16d581ca-3481-4ea0-bf63-07a064d37a46)

# 7. Error Handling using Internal Exceptions and External Exceptions

## Internal exceptions/system defined exceptions(Defined by oracle)
### 1. NO_DATA_FOUND EXCEPTION

EXAMPLE :-

first we have created and inserted data in table :-

![Screenshot 2023-11-16 173855](https://github.com/ankit35136/rdbms-practical2/assets/146933815/9ae7a305-df8c-43f5-af2d-b317e8940a72)


now we will write exception handling code for no data :-

![Screenshot 2023-11-16 174015](https://github.com/ankit35136/rdbms-practical2/assets/146933815/28f7b968-a692-4f23-b30e-123678822430)

### 2. ZERO_DIVIDE exception

creating and insertin values in table  :-

![Screenshot 2023-11-16 174238](https://github.com/ankit35136/rdbms-practical2/assets/146933815/dea2627f-71c3-47eb-be07-d6b2489273a5)

writing exception :-

![Screenshot 2023-11-16 175305](https://github.com/ankit35136/rdbms-practical2/assets/146933815/c0fe06c5-f1c8-4827-8ae8-235b7d1b5f6a)

## 2. External exceptions( user defined exceptions)

1. Raise exception
 
![Screenshot 2023-11-16 175601](https://github.com/ankit35136/rdbms-practical2/assets/146933815/eb0656f2-95e6-4972-96ab-6ea82e2967ec)

2. Raise_application_error

![Screenshot 2023-11-16 175806](https://github.com/ankit35136/rdbms-practical2/assets/146933815/342d74a3-91f8-404e-a12c-c5e8c376a9f2)

# 8. Using various types of Cursors
## A cursor is a pointer to this context area. PL/SQL controls the context area through a cursor. A cursor holds the rows (one or more) returned by a SQL statement. The set of rows the cursor holds is referred to as the active set.

two types of cursors
1. Impicit cursors
2. explicit cursors

### implicit Attribute & Description
1	
%FOUND

Returns TRUE if an INSERT, UPDATE, or DELETE statement affected one or more rows or a SELECT INTO statement returned one or more rows. Otherwise, it returns FALSE.

2	
%NOTFOUND

The logical opposite of %FOUND. It returns TRUE if an INSERT, UPDATE, or DELETE statement affected no rows, or a SELECT INTO statement returned no rows. Otherwise, it returns FALSE.

3	
%ISOPEN

Always returns FALSE for implicit cursors, because Oracle closes the SQL cursor automatically after executing its associated SQL statement.

4	
%ROWCOUNT

Returns the number of rows affected by an INSERT, UPDATE, or DELETE statement, or returned by a SELECT INTO statement.

### SQL%ROWCOUNT attribute to determine the number of rows affected −

![Screenshot 2023-11-16 100114](https://github.com/aman7935/rdbms-practical/assets/146933698/89c362bd-2a4b-4fe6-9789-6a5adb080343)

OUTPUT:-

![Screenshot 2023-11-16 100302](https://github.com/aman7935/rdbms-practical/assets/146933698/a348cad7-fd0b-442b-9768-e6a96d1958bd)

### Explicit Cursors

Explicit cursors are programmer-defined cursors for gaining more control over the context area. An explicit cursor should be defined in the declaration section of the PL/SQL Block. It is created on a SELECT Statement which returns more than one row.

Declaring the Cursor

![Screenshot 2023-11-16 100544](https://github.com/aman7935/rdbms-practical/assets/146933698/03dee94e-2701-44a1-8327-4aef56a30c6c)

Opening the Cursor

![Screenshot 2023-11-16 100615](https://github.com/aman7935/rdbms-practical/assets/146933698/c5878905-55bd-45dc-beee-476076b76d0a)

Fetching the Cursor

![Screenshot 2023-11-16 100641](https://github.com/aman7935/rdbms-practical/assets/146933698/f25a1c39-7c26-4f64-a80d-3d3df74afd62)


Closing the Cursor

![Screenshot 2023-11-16 100740](https://github.com/aman7935/rdbms-practical/assets/146933698/a90c5164-82b4-4b58-824c-229e955332b0)

# 9. How to run Stored Procedures and Functions

## 1. procedures 

A stored procedure is a prepared SQL code that you can save, so the code can be reused over and over again.

example :-

![Screenshot 2023-11-16 102457](https://github.com/aman7935/rdbms-practical/assets/146933698/3452cae0-6511-4bb6-8174-8ff24325cfc9)

executing a stored procedure

![Screenshot 2023-11-16 102617](https://github.com/aman7935/rdbms-practical/assets/146933698/4bf1208f-d832-441c-b040-b42e86ad98ca)

## 2. Stored functions 

Creating the stored function

![Screenshot 2023-11-16 104018](https://github.com/aman7935/rdbms-practical/assets/146933698/050acaf9-7895-48f7-92b1-80f529aa7232)

Using the stored function

![Screenshot 2023-11-16 104111](https://github.com/aman7935/rdbms-practical/assets/146933698/b7386d40-73ce-4da9-ba4b-eb33cca20a20)

# 10. Creating Packages and applying Triggers

1. Create pacakge specification

![Screenshot 2023-11-16 110230](https://github.com/aman7935/rdbms-practical/assets/146933698/5336a6ca-721d-4180-904a-1328ecfafe88)


2. create Package body

![Screenshot 2023-11-16 110252](https://github.com/aman7935/rdbms-practical/assets/146933698/a53f253d-31fe-47c1-b38c-4619c9a185d3)


#  Applying Triggers
## Row level trigger

![image](https://github.com/aman7935/rdbms-practical/assets/146933698/d261b4a6-ef1f-4715-9310-53a66640e486)

## column level trigger

![Screenshot 2023-11-16 115101](https://github.com/aman7935/rdbms-practical/assets/146933698/c27f1bfe-c197-42ec-b0b1-a3e782c0b047)
# 11. Creating Arrays and Nested Tables.
creating arrays

![Screenshot 2023-11-16 120412](https://github.com/aman7935/rdbms-practical/assets/146933698/0b03b041-bc48-48d2-883c-86ab588163de)

## Nested table
![Screenshot 2023-11-16 121359](https://github.com/aman7935/rdbms-practical/assets/146933698/7948d9e9-cd92-4a09-9552-9f92d82f9744)

